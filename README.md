# deploy With ec2 AWS
## Connect ec2
```bash 
// connect using instance public dns name
ssh -i /path/key-pair-name.pem instance-user-name@instance-public-dns-name

// connect using IPV6 address
ssh -i /path/key-pair-name.pem instance-user-name@instance-IPv6-address
```
## install git
```bash 
sudo apt install git
```
## install npm or yarn 
```bash 
cd ~
curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
nano /tmp/nodesource_setup.sh
sudo bash /tmp/nodesource_setup.sh
sudo apt install nodejs

# yarn 

npm install -g yarn -y
```

## config nginx and install
```bash 
#  for super user
sudo -s 
# - to update the existing packages
sudo apt update 
# - to install the nginx web server
sudo apt install nginx 

```

## Allocating the Elastic IP address:

## Moving the angular code to the ec2 instance use git 

## add to script package.json 
```bash 
# -> For angular version 12 and above 
"build:prod": "ng build --configuration production" 
# -> For versions older than 11
"build:prod": "ng build --prod" 
```
## build 
```bash 
# build produc
npm run build:prod

# build dev
npm run build


```


# update Config nginx 
```bash 
vi /etc/nginx/sites-enabled/default

```

### config 
```bash 
server {
        listen 80 default_server;
        listen [::]:80 default_server;      
  
        #provide the build path
        root /var/www/html/angular-demo/;
        index index.html index.htm index.nginx-debian.html;
        server_name _;
        location / {
             try_files $uri $uri/ /index.html;
        }
}

```

# restart 

```bash 
sudo service nginx restart
# check status
sudo service nginx status


```

# done