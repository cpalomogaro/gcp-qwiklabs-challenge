# gcp-qwiklabs-challenge
Guía para realizar el Quest Challenge de Qwiklabs en Google Cloud Platform

1) Google Cloud Essential Skills: Challenge Lab
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

2) Deploy a Compute Instance with a Remote Startup Script
https://www.qwiklabs.com/focuses/1735?parent=catalog

3) Configure a Firewall and a Startup Script with Deployment Manager
https://www.qwiklabs.com/focuses/1736?parent=catalog

4) Configure Secure RDP using a Windows Bastion Host
https://www.qwiklabs.com/focuses/1737?parent=catalog

5) Build and Deploy a Docker Image to a Kubernetes Cluster
https://www.qwiklabs.com/focuses/1738?parent=catalog

6) Scale Out and Update a Containerized Application on a Kubernetes Cluster
https://www.qwiklabs.com/focuses/1739?parent=catalog

7) Migrate a MySQL Database to Google Cloud SQL
https://www.qwiklabs.com/focuses/1740?parent=catalog
