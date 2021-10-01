# Getting Started with Cloud Shell and gcloud

https://google.qwiklabs.com/focuses/563?parent=catalog&qlcampaign=1s-sydney-1997


## List active account
```
# List active account
gcloud auth list

# List project-ID
gcloud config list project
```

## Configure environment
```
gcloud config get-value compute/zone
gcloud config get-value compute/region
```

### Identify default region and zone
```
gcloud compute project-info describe --project <your_project_ID>
```

### Set env variables
```
export PROJECT_ID=<your_project_ID>
export ZONE=<your_zone>

echo $PROJECT_ID
echo $ZONE
```

### Create VM with gcloud tool
```
gcloud compute instances create gcelab2 --machine-type n1-standard-2 --zone $ZONE
```

#### Command details

`gcloud compute` allows you to manage your Compute Engine resources in a format that's simpler than the Compute Engine API.

`instances create` creates a new instance.

```
gcloud compute instances create --help
```

`gcelab2` is the name of the VM.

The `--machine-type` flag specifies the machine type as n1-standard-2.

The `--zone` flag specifies where the VM is created.

If you omit the `--zone` flag, the gcloud tool can infer your desired zone based on your default properties.
Other required instance settings, such as machine type and image, are set to default values if not specified in the create command.

### Command help
```
gcloud -h
gcloud config --help
gcloud help config

gcloud config list
gcloud config list --all
gcloud components list
```

The results of the `gcloud config --help` and `gcloud help config` commands are equivalent. Both return long, detailed help.


## Task 2: Install a new component

Next, you'll install a gcloud component that makes working in the gcloud tool easier.

```
sudo apt-get install google-cloud-sdk
```

### Enable gcloud interactive shell environment
```
gcloud beta interactive
```

## Task 3: Connect to your VM instance with SSH
```
gcloud compute ssh gcelab2 --zone $ZONE
```




