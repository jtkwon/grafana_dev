# Template for Grafana Plugin Development

For some reason, @grafana/toolkit doesn't install on some latest versions.  Try downgrading npm to version 7.0.15

#### Configurations
- app/grafana.ini `To change grafana config`
- Create an .env in the root directory and add the following under `grafana` if you would like to set environment variable
```
env_file:
   - .env 
```


! After changing, .env or grafana.ini, run `docker-compose up -d` again to see the changes
! After adding a new plugin, run `docker-compose restart` to see the changes

#### To spin up Grafana
```
docker-compose up -d
```
- This will mount volume in app/data  
- Create new plugins under the `app/data/plugins` directory  
- Grafana by default will run in port 3000.  If you would like to run it under different local port, in `docker-compose.yml`, change the local port

#### To stop the Grafana
```
docker-compose stop
```

#### To stop and remove Grafana container, volume, and image associated with
```
docker-compose down -v --rmi all
```

#### Creating a new plugin project
1. `npm install` to install Grafana toolkit (OPTIONAL IF YOU DO NOT HAVE IT INSTALLED GLOBALLY)  
   A: `npm run create [name of new plugin]` (OPTIONAL IF YOU DO NOT HAVE TOOLKIT INSTALLED GLOBALLY)  
   B: With toolkit installed, create a new project under the `app/data/plugins`
2. Follow all the steps
3. Go into the new plugin directory under app/data/plugins
4. `npm install` to install dependencies
5. `npm run dev` or `npm run watch` (watch)