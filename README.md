![Screenshot](docs/profile.png)
---

# Predição do primeiro destino no AIRBNB

> Esse projeto visa construir um algoritmo que seja capaz de predizer o primeiro destino que o usuário irá escolher no Airbnb.
---
## Entendimento do problema - Modelo de negócio do AIRBNB
**Objetivo do problema:**

- 1.0 Previsão do primeiro destino que o um novo usuário irá escolher.

    - Porque?

        * Qual o tipo do modelo de negócio do Airbnb?

            * Marketplace (conectar oferta e demanda, e poder ganhar em cima dessa transação).

            * Oferta (Pessoas oferecem acomodação)

                -- Tamanho do portifólio
                -- Diversidade/densidade de portifólio.
                -- Preço médio.

            * Demanda (Pessoas procurando acomodação)

                -- Número de usuários
                -- LTV (Lifetime Value - Quanto que a pessoa vai gastar com a empresa)
                -- CAC (Client Acquisition Cost - Custo por cliente)

                Gross Revenue (Margem de lucro) = (fee * Número de usuário) - CAC
                
                **FEE => É a diferença entre o preço médio e o valor dado a pessoa que oferece a acomadação.**

- Proposta da Solução:

    - Modelo de predição do primeiro destino de um novo usuário. Tipo de entrega:

        * 1.0. Salvar a predição em tabelas no banco de dados para ser acessada por meio de uma ferramenta de visualização.
        * 2.0. Construção de API e acesso por meio dela:
        
            -- Input: Usuário coloca suas características.
            
            -- Output: Mostra as características do usuário e a **predição do destino**.

---
## Project Organization

```
├── AUTHORS.md              <- List of developers and maintainers.
├── CHANGELOG.md            <- Changelog to keep track of new features and fixes.
├── CONTRIBUTING.md         <- Guidelines for contributing to this project.
├── Dockerfile              <- Build a docker container with `docker build .`.
├── LICENSE.txt             <- License as chosen on the command-line.
├── README.md               <- The top-level README for developers.
├── configs                 <- Directory for configurations of model & application.
├── models                  <- Trained and serialized models, model predictions,
│    └──                       or model summaries.
├── notebooks               <- Jupyter notebooks. Naming convention is a number (for
│    │                         ordering), the creator's initials and a description,
│    └──                       e.g. `1.0-fw-initial-data-exploration`.
├── scr                     <- Analysis and production scripts which import the
│    └──                       actual PYTHON_PKG, e.g. train_model.
├── data
│   ├── external            <- Data from third party sources.
│   ├── interim             <- Intermediate data that has been transformed.
│   ├── processed           <- The final, canonical data sets for modeling.
│   └── raw                 <- The original, immutable data dump.
├── docs                    <- Generated analysis as HTML, PDF, LaTeX, etc. Generated plots and figures for reports.
├── environment.yml         <- The conda environment file for reproducibility. 
└── pyproject.toml          <- Build configuration. Don't change! Use `pip install -e .`
    └──                        to install for development or to build `tox -e build`.

```
---