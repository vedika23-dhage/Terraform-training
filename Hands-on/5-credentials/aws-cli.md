** Description**
* From this example we can understand how you can secure your credentials using AWS command line utility.
* To do this first we need to install `aws cli` tool in your virtual machine.
* Follow the below steps to install `aws cli`

# Configure aws cli


vagrant up terraform - to make ubuntu machine up 

vagrant ssh terraform - to login into machine

# To install in ubuntu machine
sudo apt-get update

# To install awscli
sudo apt-get install awscli

# To check version 
aws --version

- run `aws configure` command which will prompt for asking access & secret key
aws configure
- Then you can see credentials are stored as environment variable under file ~/.aws/credentials
- Just do cat  ~/.aws/credentials to view the file.

cat ~/.aws/credentials

# enter into root
sudo su
cd /vagrant/data
