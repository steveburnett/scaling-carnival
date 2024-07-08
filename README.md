* Clone the Presto repository:

  ```bash
  git clone https://github.com/prestodb/presto.git
  ```

* Run the following (should work on Linux and macOS):

  ```bash
  cd presto/presto-native-execution
  make submodules
  make conda-install-deps
  make conda-build
  make conda-test
  ```

  On Linux, conda adds initialization code to `~/.bashrc`. On macOS, it uses
  `~/.zshrc`. Internally, the `./scripts/setup-conda.sh` script is used.

* These Makefile targets support a number of options, for example:

```bash
cd presto/presto-native-execution
make submodules
make CONDA_ENV_NAME=test-conda-env \
     CONDA_INSTALL_DIR=test-install-dir \
     NUM_THREADS=16 \
     PROMPT_ALWAYS_RESPOND=Y \
     conda-install-deps
make CONDA_ENV_NAME=test-conda-env CONDA_INSTALL_DIR=test-install-dir NUM_THREADS=16 conda-build
make CONDA_ENV_NAME=test-conda-env CONDA_INSTALL_DIR=test-install-dir NUM_THREADS=16 conda-test
```

- `CONDA_ENV_NAME` is the conda environment name (default: `presto-dev`)
- `CONDA_INSTALL_DIR` is the directory where conda will be installed (default: `$HOME/miniconda3`)
- `NUM_THREADS` is the number of jobs used for building (default: number of CPUs, via `getconf _NPROCESSORS_ONLN`)
- `PROMPT_ALWAYS_RESPOND` determines if a dependency is downloaded when it already exists on disk (default: `Y`).
