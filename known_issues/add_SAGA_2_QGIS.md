# To integrate SAGA in QGIS do the following:

1. Open the `SagaAlgorithmProvider.py` file in a text edit (the file can be found in `/usr/share/qgis/python/plugins/processing/algs/saga/SagaAlgorithmProvider.py` or `/usr/share/qgis/python/plugins/sagaprovider/SagaAlgorithmProvider.py`)
2. Change the `REQUIRED_VERSION = '8.5.'`  8.5 is the current version of SAGA. You cam get currenet SAGA version using the following command from terminal `saga_cmd --version`
