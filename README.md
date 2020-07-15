# Docker image to run primer evaluation pipeline

## Files to create a docker image to run  https://github.com/MVesuviusC/primerEvaluation

Documentation is incoming

Kept here: https://hub.docker.com/repository/docker/matthewvc1/primer_eval

## Usage:

mkdir evalOut

docker run \
       -it  \
       -v databases:/usr/local/databases \
       --mount type=bind,source="$(pwd)"/evalOut,target=/home/runDir/output \
       --name primerEval \
       matthewvc1/primer_eval:6_11_2020 \
       bash
	    
###once inside, run setupDatabases.sh which should take a few hours to run

Then start R and run:

rmarkdown::render("primerEvalPipeline.Rmd",
	output_dir = "output/mam16SOut/",
	params = list(
	outDir = "output/mam16SOut",
	primerFile = "mam16SPrimerInput.txt",
	taxonomyDb = "/usr/local/databases/tax/taxonomy.db",
	threads = 8
	)
)
																      

