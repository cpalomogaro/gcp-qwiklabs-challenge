<img src="https://avatars1.githubusercontent.com/u/48249676?s=200&v=4" alt="Google Cloud Platform logo" title="Google Cloud Platform" align="right" height="96" width="96"/>

# Google Cloud Developer Community Santiago [![Slack][slack_badge]][slack_link]

[slack_badge]: https://img.shields.io/badge/slack-gcp-E01563.svg?style=flat
[slack_link]: https://join.slack.com/t/gdgcloudscl/shared_invite/enQtNDg4NjQ2NTE3NDkwLThhMTI0NmQ5NDhjMGRhMzJhNmQwZDEzNWRlNzIzMTA3YWNjMWUyY2Q2OTg1ZTk4OTZiYmNiMDU1MWNjMWZjOTM

# Guía para realizar el Quest Challenge de Qwiklabs en Google Cloud Platform


### 1) Google Cloud Essential Skills: Challenge Lab
https://www.qwiklabs.com/focuses/1734?parent=catalog

- Abrir Cloud Shell

- Obtener el ID del Proyecto ejecutando el siguiente comando:

	gcloud config list project

- Crear una variable de entorno con el Id del Proyecto:

	PROJECT_ID=[INGRESA_TU_ID_DEL_PROYECTO_AQUÍ]

- Ejecutar el siguiente comando para crear la máquina virtual:

gcloud compute --project=$PROJECT_ID instances create instance-test --zone=us-central1-a --tags=http-server

- Ejecutar el siguiente comando para crear la regla de firewall que expone la máquina virtual:

gcloud compute --project=$PROJECT_ID firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server

- Conectarse a la máquina por SSH y ejecutar el siguiente comando:

	sudo apt-get update && sudo apt-get install apache2 -y

### 2) Deploy a Compute Instance with a Remote Startup Script
https://www.qwiklabs.com/focuses/1735?parent=catalog

- Abrir Cloud Shell

- Obtener el ID del Proyecto ejecutando el siguiente comando:

	gcloud config list project

- Crear una variable de entorno con el Id del Proyecto:

	PROJECT_ID=[INGRESA_TU_ID_DEL_PROYECTO_AQUÍ]

- Crear un Storage Bucket:

	gsutil mb gs://$PROJECT_ID

- Cargar Startup Script en Cloud Shell (Ver archivo adjunto en laboratorio)

- Mover Startup Script desde Cloud Shell a Storage:

	gsutil cp resources-install-web.sh gs://$PROJECT_ID

- Ejecutar el siguiente comando para crear la máquina virtual:

gcloud compute --project=$PROJECT_ID instances create instance-test --zone=us-central1-a --tags=http-server --metadata=startup-script-url=gs://$PROJECT_ID/resources-install-web.sh --scopes=https://www.googleapis.com/auth/devstorage.read_only

- Ejecutar el siguiente comando para crear la regla de firewall que expone la máquina virtual:

gcloud compute --project=$PROJECT_ID firewall-rules create default-allow-http --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server 

### 3) Configure a Firewall and a Startup Script with Deployment Manager
https://www.qwiklabs.com/focuses/1736?parent=catalog

### 4) Configure Secure RDP using a Windows Bastion Host
https://www.qwiklabs.com/focuses/1737?parent=catalog

### 5) Build and Deploy a Docker Image to a Kubernetes Cluster
https://www.qwiklabs.com/focuses/1738?parent=catalog

### 6) Scale Out and Update a Containerized Application on a Kubernetes Cluster
https://www.qwiklabs.com/focuses/1739?parent=catalog

### 7) Migrate a MySQL Database to Google Cloud SQL
https://www.qwiklabs.com/focuses/1740?parent=catalog
