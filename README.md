# Example training workflow on SkyPilot
This repo contains an example training workflow consisting of three simple SkyPilot tasks:
1. `data_preprocessing`: Ingests data and writes it to a bucket.
2. `train`: Trains a model on the data.
3. `eval`: Evaluates the model. Can be optionally run on the same cluster as `train`.

These tasks don't actually run any code, but they demonstrate how to structure a training workflow on SkyPilot.

## Usage

When developing the workflow, you can run the tasks independently using `sky launch`:

```bash
$ sky launch -c data data_preprocessing.yaml
...
```

The train and eval step can be run in a similar way, and the eval step can be run on the same cluster as the train step by setting the `--cluster` flag:

```bash
$ sky launch -c train train.yaml
...
# Run eval on the same cluster as train
$ sky exec train eval.yaml
```
