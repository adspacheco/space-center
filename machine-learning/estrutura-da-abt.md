# Estrutura da ABT

A Tabela Base Analítica (ABT) é um conjunto de dados estruturado utilizado para resolver problemas específicos como churn, fraude e atraso na entrega.&#x20;

<figure><img src="../.gitbook/assets/ok.png" alt=""><figcaption><p>ABT</p></figcaption></figure>

Cada linha da ABT representa uma entidade do problema, como clientes ou pedidos, e as colunas correspondem às características (features) que descrevem essas entidades, como frequência de compras, valor de pedidos, tempo de transação, entre outros.&#x20;

No contexto apresentado, a base histórica de dados utilizada para construir as features vai de 01/2017 a 06/2018, sendo que a safra de referência para essas features é de 01/2017 a 12/2017. O target, ou seja, o resultado que se deseja prever, é definido olhando 6 meses à frente, até 06/2018.&#x20;

Por exemplo, para prever o churn, a frequência e o valor das compras de um cliente são analisados para determinar se ele não revenderá nos próximos seis meses.&#x20;

Essa análise permite que algoritmos de aprendizado de máquina identifiquem padrões e façam previsões precisas sobre o comportamento futuro das entidades, auxiliando na tomada de decisões estratégicas.

## Construção da ABT

* Base histórica para features: De 05/01/2017 a 30/06/2018.
* Safra de referência para features: De 05/01/2017 a 31/12/2017.
* Target definido para o período subsequente, até 30/06/2018.

```python
features = hist_abt.query('DATE' < '2018-01-01')
                   .groupby('SELLER_ID')
                   .agg({
                       'DT_ULT_VD': ('DATE', 'MAX'),
                       'UF': ('SELLER_STATE', 'FIRST'),
                       'ORDERS_12M': ('ORDER_ID', 'NUNIQUE')
                   })
                   .assign(DT_SAFRA_REF=pd.to_datetime('2018-01-01'))
                   .assign(RECENCIA=lambda df: df.memory['DT_ULT_VD'])
                   .reset_index()

target = hist_abt.query('DATE' >= '01-01-2018' & 'DATE' < '2018-07-01')
                 .filter(['SELLER_ID'])
                 .drop_duplicates()
```

* Realizar o join para integrar o target e features, organizando as colunas.

```python
df_abt = df.merge(target, on='SELLER_ID', how='left', indicator=True)
           .assign(NAO_VENDEU_6M=lambda df_memo: np.where(df_memo['merge'] == 'left_only', 1, 0))
```
