# Titans-MaAS

Experiments go in `/experiments`. An experiment represents a set of changes to the research process (e.g. architectures, anything we want to explore meanwhile) and the sequence of experiments over time represents a complete record of the development process. Each experiment should be self-contained and reproducible. 

You can run experiments from the root of the project, e.g. `python -m experiments.mv_prototype`

Main files go in `/main` [to be replaced with our actual research project name, after we've finalized our proposal]. Please keep this clean as we will primarily use this as the frontface of our research. This directory contains the core implementation and stable code that other experiments can build upon.

## Setup

This project supports multiple package managers. Choose the one that works best for your setup:

### Using uv 
```bash
uv sync

uv run python main.py
```

### Using pip
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

pip install -e .

python main.py
```

### Using poetry
```bash
poetry install

poetry run python main.py
```

### Set up pre-commit hooks
After installation, set up the pre-commit hooks to ensure code quality:

```bash
# With uv
uv run pre-commit install

# With pip
pre-commit install

# With poetry
poetry run pre-commit install
```

## Usage

For experiments, create a new directory under `/experiments` with your initials and the experiment name i.e. `/experiments/{initials}_mixture_of_experts` if you're experimenting with adding Mixture of Experts (MoE) or `/experiments/{initials}_new_dataset` if you're adding a new dataset.

## Development

The project uses ruff for linting and formatting. Pre-commit hooks will automatically run when you commit changes. You can also run them manually:

### Using uv:

```bash
uv run pre-commit run --all-files
uv run ruff check .
uv run ruff format .
```

### Using pip:
```bash
ruff check .
ruff format .
ruff check --fix .
```

### Using poetry:
```bash
poetry run ruff check .
poetry run ruff format .
poetry run ruff check --fix .
```

## Dependencies

Core dependencies include:
- PyTorch for deep learning
- Transformers for NLP models
- NumPy for numerical computing
- Pydantic for data validation
- Requests for HTTP operations
