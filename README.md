# PacBio Apps Container
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/1243)

A container for installing and running PacBio applications using Conda.

To use the container:
```
module load pacbioapps/latest
```

Use the included wrapper script ```runpbapps``` to run commands (e.g., blasr):

```
runpbapps blasr --version
```


