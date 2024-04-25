# Arquitetura de Pastas (MVC)

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

A pasta raiz `/src` serve como o núcleo central, onde a lógica HTTP divide-se em `Controllers` para as rotas e `Models` para a lógica de dados. O `Server File` é o ponto de entrada da aplicação. Em `db`, temos `Connection` para os conectores do banco de dados e `Migrations` para scripts de atualização. `Tests` é dedicada a testes automatizados. Por fim, `deploy` contém ferramentas e scripts para implantar a aplicação em diferentes ambientes.
