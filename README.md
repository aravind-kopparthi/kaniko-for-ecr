For Kaniko to push Docker images to ECR it requires an additional config file. 
This project adds that config file to the official Kaniko Docker image.

## Running

Here's an example which:
1. Pulls a Dockerfile & context from S3
2. Builds the image
3. Pushes the image to ECR

`docker run --rm -v /home/<user-home>/.aws:/root/.aws tkgregory/kaniko-for-ecr:latest --context s3://<your-bucket>/<your-object-prefix>.tar.gz --context-sub-path <your-context-sub-path> --destination <your-ecr-repository-uri>:latest`

## More info

* [Kaniko official documentation](https://github.com/GoogleContainerTools/kaniko)
* [Building container images on Amazon ECS on AWS Fargate](https://aws.amazon.com/blogs/containers/building-container-images-on-amazon-ecs-on-aws-fargate/) explains how to run a Kaniko container to push to ECR
