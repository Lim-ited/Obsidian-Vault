from qiskit_ibm_runtime import QiskitRuntimeService

QiskitRuntimeService.save_account(
    token="6zignlXlOhedHHPr2gByc0G8xcLW2mU3mpcW6F5tLYzs",
    instance="crn:v1:bluemix:public:quantum-computing:us-east:a/a9b97467e1764d528c81e4fb88381d3e:57010fe3-8b5c-4f7b-a462-ec130b618cc9::",
    set_as_default = True,
    overwrite = True
    )

service = QiskitRuntimeService()