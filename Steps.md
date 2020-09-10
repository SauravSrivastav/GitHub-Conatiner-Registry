Step1: First we need to generate PAT(Personal Access Tokens) token 
       User Settings -> Developer Settings
       The PAT token will help you to authenticate with GitHub.

Step2: Assign the corrections permissions to the Token. We need to provide correct permission to push the   image to the registry:
       write,read,delete packages etc.

Step3: Now save securely PAT & it is recommended to store it in our environment variables in the machine where docker is running:
> $ export CR_PAT=YOUR_TOKEN

Step4: Login into GitHub Container Registry using below command in the machine:
> $ echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin

Step5: Build the docker image and tag with following name convention:
# docker build -t ghcr.io/OWNER/IMAGE_NAME:VERSION .
> docker build -t ghcr.io/sauravsrivastav/gcrtest:1.0 .

Step 6: Push the image to the registry
docker push ghcr.io/sauravsrivastav/gcrtest:1.0

# Once we pushed the image, it will available in the packages section in GitHub Home Page.

