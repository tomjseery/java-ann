# Java ANN

An educational artificial neural network implemented directly in Java. The project trains a single-hidden-layer feed-forward network for regression, using handwritten forward propagation, backpropagation and parameter-update strategies rather than a machine-learning framework.

The repository also contains the spreadsheet preprocessing used by the network and a linear-regression baseline for comparing mean squared error.

## Implemented training strategies

- Fixed learning rate (`Basic`)
- Momentum
- Annealed learning rate
- Bold-driver adaptive learning rate
- Weight decay
- Train, validation and test evaluation using mean squared error
- Predicted-versus-actual and error-history exports to Excel

## Repository layout

| Path | Purpose |
| --- | --- |
| `BackPropagation/` | Neural-network implementation, datasets and NetBeans/Ant project |
| `BackPropagation/src/backpropagation/` | Forward pass, backpropagation and training-strategy classes |
| `DataStandardisation/` | Spreadsheet preprocessing and min-max scaling utility |
| `Report.pdf` | Original project report and experimental discussion |

## Running the included build

The historical NetBeans build targets Java 8 and bundles its Apache POI dependencies in `BackPropagation/dist/lib`.

From the repository root:

```sh
cd BackPropagation
java -jar dist/BackPropagation.jar
```

Run it from `BackPropagation` because the application reads `TrainingData.xlsx`, `ValidationData.xlsx` and `TestingData.xlsx` from the current directory. The default entry point runs the basic network configuration; the other strategies can be selected in `BackPropagation.java`.

To rebuild the project, open `BackPropagation` in NetBeans or update its Ant library paths for your machine. The checked-in NetBeans metadata contains paths from the original development environment.

## Model shape

The implementation accepts a configurable number of inputs and hidden units, followed by one sigmoid output. It standardises the supplied data, trains against the spreadsheet rows and reports de-standardised regression results. This is deliberately a focused implementation for studying ANN mechanics, not a general-purpose neural-network library.

## Status

This is archived university coursework. Generated class files, a prebuilt JAR and experimental spreadsheets are retained to preserve the original runnable project.
