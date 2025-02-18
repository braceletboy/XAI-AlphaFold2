# XAI-AlphaFold2
This repository contains the code for reproducing the results for the paper "An Exploratory Investigation into Explainable AI for Protein Folding Predictions"

This project uses `pipenv` to manage its dependencies. For details on how to install and use pipenv check out the [official documentation][1]. If you already have pipenv you can install the dependencies from the Pipfile using:
```bash
pipenv install --dev
```

After the dependencies are installed, you can install the alphafold, colabfold and prody and pdbfixer packages (which are not part of the pipfile) using `pip` once you are inside the pipenv environment. This needs to be done to handle some dependency errors that pipenv is unfortunately unable to resolve. Then, the notebooks to run the experiments can be found in the `Runs/` folder.


[1]: https://pipenv.pypa.io/en/latest/
