# Files to create a docker image to run  https://github.com/MVesuviusC/primerEvaluation

Documentation is incoming

Kept here: https://hub.docker.com/repository/docker/matthewvc1/primer_eval


docker run -it  -v databases:/usr/local/databases -v output:/home/runDir/output --name primerEval matthewvc1/primer_eval:0.1.2 bash
