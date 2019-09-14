# AWS
Amazon Web Services.

## Required Softwares
- [Putty](https://www.putty.org/)
- [WinSCP](https://winscp.net/eng/download.php)
- Install both putty and winscp.

### Step 1: Start a new Ubuntu Linux server instance on Amazon EC2

- Login to AWS Educate Account.
- Select EC2 Service.
- Then launch Instance with appropriate settings.
- And then download .pem file then place it at perticuler folder.

### Step 2: Convert .PEM file to  .PPK File.

- After installing putty search for puTTygen in your pc then click on open
- Click on load and then upload the generated pem file
- Click on save private key and then close puttygen

### Step 3:Connect to Remote Server from Local Machine using .PPK File

- Open putty 
- Copy the Public IP Address from EC2 instance and paste it in the Host Name
- Expand SSH and select AUTH and then browse for .PPK File then click on OK
- It will open termial wait for Username Enter 'ubuntu' as Username
- Enter the command 'sudo su' to connect super user

## Secure the server

### Step 4: Update and upgrade installed packages

```
sudo apt-get update
sudo apt-get upgrade
```
### Install apache2 server.
```
sudo apt-get install apache2
```
### Change Apache2 index.html Permissions
```
chmod 777 /var/www/html
```
### Restart the server
```
sudo service  apache2 restart
```
- Place your Public IP Address or DNS at URL whether it is working or not 

### Step 5: Using WinSCP

- Open WinSCP and enter the required details as below
- Enter the Hostname as 'Public IP Address'
- Enter usename as 'ubuntu'
- To enter the password click on advanced option then goto SSH select Authentication and click on Browse
- Open the saved .PPK file and click on OK
- Click on Login
- It will shows Local Machine at left hand side and Remote Machine on Right hand side.
- At local machine choose your project location
- At right hand side change page location from 'ubuntu' to 'root'
- Change the 'root' path '/var/www/html'
- Delete the default Apache2 page i.e.,index.html 
- At Local Machine(left hand side) select all your project files then drop it in the Remote server(Right hand side /var/www/html) 
- Go back to your ubuntu terminal 
- Restart Apache2 server
```
sudo service apache2 restart
```
- Place your Public IP Address or DNS at URL whether your project is displaying or not 
