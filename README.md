# ibmcloud-kubernetes
Step by Step to deploy a Container into Kubernetes, IBM Cloud


### Welcome!
Let's get started by installing the needed CLIs, setting up your first private registry namespace, and pushing your first image.

### Install, Set Up, and Log In
1. [Install the IBM Cloud CLI](https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)

2. [Install the Docker CLI.](https://docs.docker.com/engine/installation/)

3. Install the Container Registry plug-in.

`ibmcloud plugin install container-registry -r Bluemix`

4. Log in to your IBM Cloud account.

`ibmcloud login -a https://cloud.ibm.com`

_If you have a federated ID, use ibmcloud login --sso to log in to the IBM Cloud CLI._

5. Choose a name for your first namespace, and create that namespace. Use this namespace for the rest of the Quick Start.

`ibmcloud cr namespace-add <my_namespace>`

### Push the image to your private registry
1. Log your local Docker daemon into the IBM Cloud Container Registry.

`ibmcloud cr login`

2. Push a test image from Docker Hub.

`docker push yeasy/simple-web`

3. Pull the test image from Docker Hub.

`docker pull yeasy/simple-web`

4. Choose a repository and tag by which you can identify the image. Use the same repository and tag for the rest of this Quick Start.

`docker tag yeasy/simple-web:latest us.icr.io/<my_namespace>/simple-web:latest`

5. Push the image.

`docker push us.icr.io/<my_namespace>/simple-web:latest`

6. Verify that your image is in your private registry.

`ibmcloud cr image-list`

