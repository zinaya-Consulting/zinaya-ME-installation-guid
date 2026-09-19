# zinaya-ME-patch-guid

**Zinaya ME** is a containerized monitoring and evaluation dashboard platform designed for managing, tracking, and visualizing survey fieldwork operations in real time.

# Patching the system
you are provided with a zip file containing `dhs_dashboard.tar` and `docker_patch.sh`, extract the zip and copy those two files to the server in the same folder named `Zinaya-ME` or `<country-code>-Zinay-ME`.

**NOTE**: Always patch files must be in `Zinaya-ME` or `<country-code>-Zinay-ME` on the server before you start the patching process.

## 1. Patching the docker
#### step 1: give docker_patch.dsh required permissions

```
sudo chmod 777 docker_patch.sh
```

#### step 2: run the file
```bash
./docker_patch.sh
```


## 2. Patching Dashboard

#### step 1. Load the Image

```
sudo docker load -i dhs_dashboard.tar
```

#### 2. Reload the demon
```
sudo systemctl daemon-reload
```
#### 3. Restart the dashboard service file

here you need to restart the dashboard to reflect the changes, run `sudo service dhs_dashboard restart` or `sudo service <country-code>_dhs_dashboard restart` 
```
sudo systemctl restart dhs_dashboard
```

#### NOTE:
* If your dashboard service is not running as `dhs_dashboard` you may need to change the above command to the correct name and if you don't remember it's name, use `sudo docker ps` and find the name given to your dashboard service and edit the above command to match you dashboard service name.

