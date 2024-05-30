# Safras na ABT

A estrutura de safras na Tabela Base Analítica (ABT) é um método utilizado para a criação de features e targets de forma escalonada ao longo do tempo.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-05-30 at 16.33.12@2x (1).png" alt=""><figcaption></figcaption></figure>

Cada safra representa um período de tempo contínuo onde as features são extraídas de dados históricos e o target é projetado para um período futuro subsequente.&#x20;

Por exemplo, a Safra 1 utiliza dados históricos de janeiro de 2017 a dezembro de 2017 para gerar features e projeta o target de janeiro de 2018 a junho de 2018. A

&#x20;Safra 2, de fevereiro de 2017 a janeiro de 2018, projeta o target de fevereiro de 2018 a julho de 2018, e assim sucessivamente.&#x20;

Esse processo permite criar várias janelas de observação e previsão, garantindo que o modelo preditivo tenha uma base robusta e diversificada para identificar padrões e tendências.&#x20;

A abordagem de safras é fundamental para construir modelos de previsão de alta precisão, adaptando-se a variações temporais e comportamentais nas entidades analisadas.
