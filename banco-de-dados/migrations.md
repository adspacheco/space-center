# Migrations

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Migrations: processo de aplicação de alterações sistemáticas e controladas nas estruturas de dados.&#x20;

O processo inicia-se com a <mark style="background-color:blue;">**criação**</mark> de uma migração, que estabelece um conjunto de alterações a serem aplicadas ao banco de dados. Segue-se a etapa de <mark style="background-color:green;">execução</mark>, que pode ser dividida em dois tipos de execuções: _<mark style="color:green;">**Dry Run**</mark>_ e _<mark style="color:green;">**Live Run**</mark>_.&#x20;

"Dry Run" é uma execução simulada que não altera o banco de dados, servindo para verificar a integridade e a viabilidade das alterações propostas sem risco de corromper dados existentes. Por outro lado, um "Live Run" é uma implementação real das alterações, modificando efetivamente o banco de dados.&#x20;

No contexto da execução, esse processo pode ser orientado por APIs, utilizando métodos "get" para recuperar informações sobre o estado atual das migrações e "post" para aplicar as migrações de fato.

\
