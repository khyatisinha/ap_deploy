# ap_deploy

Step1: Select a pre-trained model
The pretrained model selected is Keras ResNet50 with 50 deep neural network layers.The model is selected to make predictions as it gives extremely good performance and is not computationally intensive because of the residual architecture.

Step2: Select an AWS Instance
Selected a Free Tier AMI

Step3: Setting up SSH key
Private Key is required for SSH Connection from linux (Generate and store private key (~/.ssh – recommended)
SSH from putty or gitbash…etc (terminal emulator) (Used – gitbash)

Step4: Start docker, create docker container and generate Image 
$sudo yum update -y //update the installed packages
$sudo amazon-linux-extras install docker //Install the most recent docker package
$sudo service docker start //start docker service
$sudo usermod -a -G docker ec2-user //add user to the docker group
$touch Dockerfile //Docker file used to create container or base image to use for docker image

Step5 :Run the model and save the output to a file
The keras_resnet.py downloads the pretrained keras resnet50 model and makes prediction on the input image.
The input image fed is a Green apple which is predicted correctly with a confidence of more than 99%.
Along with the correct prediction, the code also displays the top 4 potential predictions made on the test image.
The output is redirected to a log file with the below command:-
$ docker logs 93228e923ff3 | tee log // redirecting the docker log output to log

