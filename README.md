This is an Example to build only specific MicroServices depending on the code changes in a MonoRepo with a single Cloud Build Trigger.

This Repo has 
1. A Base CloudBuild.yaml which acts as a trigger for the CI pipeline.
2. Two Microservices service-one and service-two with their respective manifests file and cloud build file to build that specific microservice.

Once the CloudBuild is Triggered, The CloudBuild first identifies the directory changes from a git diff and writes to a local text file to pass on the next step.

In the next step, the Text file is read and the cloudbuild file path is built with the format as <directory>/cloudbuild.yaml. Then the builds are submitted via gcloud Options which would then do a build for each of the specific Microservice.

