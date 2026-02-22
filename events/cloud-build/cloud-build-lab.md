lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-create-cloud-build-storage-lab.json
lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-update-cloud-build-storage-lab.json
- Code from the ibcom-lab/entityos-cloud-build repo

0/ DELETE DB IF IT EXISTS - LAB ONLY.

!!! lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-execute-drop-data-base-lab.json

1/ CREATE DB

lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-base-create-lab.json

2/ CREATE MODEL

*Do 500 at a time*

lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-create-lab.json
	- lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-update-lab.json

lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-information-lab.json

3/ INITIALISE DB / GENESIS & SYSTEM DATA

lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-initialise-genesis-lab.json
	- lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-initialise-genesis-check-lab.json
	- lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-information-genesis-lab.json

*Do 100 at a time*
lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-model-initialise-system-lab.json

4/ DB QUERY / EXECUTE

lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-query-lab.json
lambda-local -l index.js -t 9000 -e events/lab/cloud-build/event-aws-lambda-function-invoke-cloud-build-storage-data-execute-drop-lab.json



----

lab-rds-cluster-001-aurora-serverless-v2.cluster-???.ap-southeast-2.rds.amazonaws.com
lab-rds-cluster-001-aurora-serverless-v2.cluster-???.ap-southeast-2.rds.amazonaws.com

Todo:
when creating creating the cluster add 3306 rule to self SG
create function set longer timeout