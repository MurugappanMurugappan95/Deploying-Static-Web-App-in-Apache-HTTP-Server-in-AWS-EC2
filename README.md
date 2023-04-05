# Deploying-Static-Web-App-in-Apache-HTTP-Server-AWS-EC2
Deploying the static web application in AWS EC2 instance (running in IP address 3.145.49.222 and this can be down anytime)

Follow the below commands in order to run the static web app in apahce http server in AWS EC2

# sudo su
Run above command to Switch to the root user

# sudo apt update
Run above command to update all the packages before installing apache2 web server

# sudo apt install apache2
Run above command to install apache2 web server to run the static web application

# apache2 -version
Run above command to check the version of apache2 web server and also to check whether apache2 server is installed (If not installed, then this command will throw error)

# sudo systemctl start apache2
Run above command to start the installed apache2 web server

# sudo systemctl status apache2
Run above command to check the status/ state of the apache2 web server (whether it is running or not)

# curl https://www.google.co.in/
Run above command to get the html file from the google website (can use any website for practical purpose) and the copy the response displayed 
in the terminal to use in index.html file

# cd /var/www/html
Run above command to change the directory where the index.html is available to create a static web application

# cat > index.html (and then right click)
Run above command and paste the copied response and overwrite the contents already available in index.html and now the website is up and running 
in the apache2 web server installed in the aws ec2 instance

Still, Static website cannot be accessed from the internet because the HTTP server port 80 is not allowing traffic from the end users

To allow the traffic from anywhere in the internet, We need to configure inbound rules in ec2 instance under security group tagged to the EC2 with http (TCP protocol) type of port 80

![image](https://user-images.githubusercontent.com/77397177/230161527-f52f4655-d4f0-4755-94a9-932877c3a8a1.png)

Now, the static web application can be accessed from the internet with the help of the aws EC2 instance public IP address

![image](https://user-images.githubusercontent.com/77397177/230162333-51472c81-e587-44ce-a5e8-460f21e9d4d8.png)


The future scope of this deployment can be implemented with AWS Route53 Domain Name Systems and will be application up and running in AWS cloud.
