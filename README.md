# aws-lambda-python-docker

Documentation: [Deploy Python Lambda functions with container images](https://docs.aws.amazon.com/lambda/latest/dg/python-image.html#python-image-instructions)

## Test the image locally

1 - Start the Docker image with the docker run command. In this example, docker-image is the image name and test is the tag.

```bash
docker run -p 9000:8080 docker-image:test
```

This command runs the image as a container and creates a local endpoint at `localhost:9000/2015-03-31/functions/function/invocations`.

2 - From a new terminal window, post an event to the following endpoint using a curl command:

```bash
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{}'
```

3 - This command invokes the function with an empty event and returns a response. If you're using your own function code rather than the sample function code, you might want to invoke the function with a JSON payload. Example:

```bash
curl "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{"payload":"hello world!"}'
```

3 - Get the container ID.

```bash
docker ps
```

4 - Use the docker kill

command to stop the container. In this command, replace 3766c4ab331c with the container ID from the previous step.

```bash
docker kill 3766c4ab331c
```
