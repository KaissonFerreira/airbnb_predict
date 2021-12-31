[![Project generated with PyScaffold](https://img.shields.io/badge/-PyScaffold-005CA0?logo=pyscaffold)](https://pyscaffold.org/)
<!-- These are examples of badges you might also want to add to your README. Update the URLs accordingly.
[![Built Status](https://api.cirrus-ci.com/github/<USER>/airbnb_predict.svg?branch=main)](https://cirrus-ci.com/github/<USER>/airbnb_predict)
[![ReadTheDocs](https://readthedocs.org/projects/airbnb_predict/badge/?version=latest)](https://airbnb_predict.readthedocs.io/en/stable/)
[![Coveralls](https://img.shields.io/coveralls/github/<USER>/airbnb_predict/main.svg)](https://coveralls.io/r/<USER>/airbnb_predict)
[![PyPI-Server](https://img.shields.io/pypi/v/airbnb_predict.svg)](https://pypi.org/project/airbnb_predict/)
[![Conda-Forge](https://img.shields.io/conda/vn/conda-forge/airbnb_predict.svg)](https://anaconda.org/conda-forge/airbnb_predict)
[![Monthly Downloads](https://pepy.tech/badge/airbnb_predict/month)](https://pepy.tech/project/airbnb_predict)
[![Twitter](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&label=Twitter)](https://twitter.com/airbnb_predict)
-->

# airbnb_predict

> Add a short description here!

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

## Installation

In order to set up the necessary environment:

1. review and uncomment what you need in `environment.yml` and create an environment `airbnb_predict` with the help of [conda]:
   ```
   conda env create -f environment.yml
   ```
2. activate the new environment with:
   ```
   conda activate airbnb_predict
   ```

> **_NOTE:_**  The conda environment will have airbnb_predict installed in editable mode.
> Some changes, e.g. in `setup.cfg`, might require you to run `pip install -e .` again.


Optional and needed only once after `git clone`:

3. install several [pre-commit] git hooks with:
   ```bash
   pre-commit install
   # You might also want to run `pre-commit autoupdate`
   ```
   and checkout the configuration under `.pre-commit-config.yaml`.
   The `-n, --no-verify` flag of `git commit` can be used to deactivate pre-commit hooks temporarily.

4. install [nbstripout] git hooks to remove the output cells of committed notebooks with:
   ```bash
   nbstripout --install --attributes notebooks/.gitattributes
   ```
   This is useful to avoid large diffs due to plots in your notebooks.
   A simple `nbstripout --uninstall` will revert these changes.


Then take a look into the `scripts` and `notebooks` folders.

## Dependency Management & Reproducibility

1. Always keep your abstract (unpinned) dependencies updated in `environment.yml` and eventually
   in `setup.cfg` if you want to ship and install your package via `pip` later on.
2. Create concrete dependencies as `environment.lock.yml` for the exact reproduction of your
   environment with:
   ```bash
   conda env export -n airbnb_predict -f environment.lock.yml
   ```
   For multi-OS development, consider using `--no-builds` during the export.
3. Update your current environment with respect to a new `environment.lock.yml` using:
   ```bash
   conda env update -f environment.lock.yml --prune
   ```
## Project Organization

```
├── AUTHORS.md              <- List of developers and maintainers.
├── CHANGELOG.md            <- Changelog to keep track of new features and fixes.
├── CONTRIBUTING.md         <- Guidelines for contributing to this project.
├── Dockerfile              <- Build a docker container with `docker build .`.
├── LICENSE.txt             <- License as chosen on the command-line.
├── README.md               <- The top-level README for developers.
├── code
│  ├── configs                 <- Directory for configurations of model & application.
│  ├── tests                   <- Unit tests which can be run with `pytest`.
│  ├── models                  <- Trained and serialized models, model predictions,
│  │                              or model summaries.
│  ├── notebooks               <- Jupyter notebooks. Naming convention is a number (for
│  │                              ordering), the creator's initials and a description,
│  │                              e.g. `1.0-fw-initial-data-exploration`.
│  ├── scripts                 <- Analysis and production scripts which import the
│  │                              actual PYTHON_PKG, e.g. train_model.
├── data
│   ├── external            <- Data from third party sources.
│   ├── interim             <- Intermediate data that has been transformed.
│   ├── processed           <- The final, canonical data sets for modeling.
│   └── raw                 <- The original, immutable data dump.
├── docs                    <- Directory for Sphinx documentation in rst or md.
├── environment.yml         <- The conda environment file for reproducibility.
├── pyproject.toml          <- Build configuration. Don't change! Use `pip install -e .`
│                              to install for development or to build `tox -e build`.
├── references              <- Data dictionaries, manuals, and all other materials.
├── reports                 <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures             <- Generated plots and figures for reports.
├── setup.cfg               <- Declarative configuration of your project.
├── setup.py                <- [DEPRECATED] Use `python setup.py develop` to install for
│                              development or `python setup.py bdist_wheel` to build.
├── .coveragerc             <- Configuration for coverage reports of unit tests.
├── .isort.cfg              <- Configuration for git hook that sorts imports.
└── .pre-commit-config.yaml <- Configuration of pre-commit git hooks.
```

<!-- pyscaffold-notes -->

## Note

This project has been set up using [PyScaffold] 4.1.1 and the [dsproject extension] 0.7.1.

[conda]: https://docs.conda.io/
[pre-commit]: https://pre-commit.com/
[Jupyter]: https://jupyter.org/
[nbstripout]: https://github.com/kynan/nbstripout
[Google style]: http://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings
[PyScaffold]: https://pyscaffold.org/
[dsproject extension]: https://github.com/pyscaffold/pyscaffoldext-dsproject
