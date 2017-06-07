# Let's Flask it Up!

### Docker style

#### Clone: 
`$ git clone https://github.com/timmyreilly/Flask-Ubuntu-Docker.git`

#### To Build: 
`$ docker build -t username/webappname:latest . `

#### To Start Locally: (interactive)
`$ docker run -i -p 8080:80 username/webappname:latest` 

#### To See the running instance:
`$ docker ps`

#### To Kill:
`$ docker kill [thirsty_mayer or CONTAINER ID]`  

CONTAINER ID found by running `docker ps`, output for `docker ps` looks like

```sh
billg@windoughs:~$ docker ps
CONTAINER ID         IMAGE                         COMMAND             CREATED               STATUS              PORTS                                     NAMES
1e02f5b4169e         timmyreilly/flaskweb:latest   "python main.py"    About a minute ago    Up About a minute   443/tcp, 8080/tcp, 0.0.0.0:8080->80/tcp   cranky_galileo
```

#### To Push to Docker:

`docker push username/webappname:tag `


## To deploy to Azure: 

1. Create new resource by searching Linux App: 

<kbd>
<img src="http://imgur.com/uqxNizy.png" width="800">
</kbd>

2. Give the app a *name*, *resource group* and new *app service plan*. You can configure the container now or later, but if you do it later you'll have to remove the *application settings* for Node 4.5 or whatever has been defaulted. 

<kbd>
<img src="http://imgur.com/i7aPq5q.png" width="800">
</kbd> 

Here you can see I set it to point to `timmyreilly/flaskweb:latest` this will pull the container containing very basic flask app that serves a photo and uses NGINX. 

3. Visit the completed site: 
http://yoursitename.azurewebsites.net !

If you used my container it should look like this: 

<kbd>
<img src="http://imgur.com/ovPlyGx.png" width="800">
</kbd> 



