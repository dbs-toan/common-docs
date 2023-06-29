# deploy to server dev
1. unzip dir deploy at the root of your project
  
2. run command 
```
chmod +x ./deploy/deploy.sh
chmod 600 ./deploy/ssh_key
```

3. run deploy command using
```
./deploy/deploy.sh dev
```
```dev``` is any branch you want to deploy to the dev server
