[![Deploy to EC2](https://github.com/amurpo/desafio2-devops/actions/workflows/ec2.yml/badge.svg)](https://github.com/amurpo/desafio2-devops/actions/workflows/ec2.yml)

# EC2 Deploy GitHub Action

Este repositorio incluye un flujo de trabajo de GitHub Actions que permite desplegar una instancia EC2 en AWS cada vez que se realiza un push en la rama `main`. El flujo de trabajo también crea una AMI (Amazon Machine Image) personalizada de la instancia EC2.

## Requisitos

Antes de usar este flujo de trabajo, asegúrate de tener configurados los siguientes elementos en GitHub:

1. **Claves de acceso de AWS**: Debes agregar tus claves de acceso de AWS a los secretos de GitHub.
   - `AWS_ACCESS_KEY_ID`: Tu clave de acceso AWS.
   - `AWS_SECRET_ACCESS_KEY`: Tu clave secreta de acceso AWS.

2. **Variables de entorno**: Las siguientes variables deben estar configuradas para que el flujo de trabajo funcione correctamente:
   - `IMAGE_ID`: ID de la imagen de Amazon EC2 que deseas usar.
   - `KEY_NAME`: Nombre de la clave SSH para acceder a la instancia EC2.
   - `SECURITY_GROUP_ID`: ID del grupo de seguridad de AWS que se asignará a la instancia.
   - `SUBNET_ID`: ID de la subred de AWS donde se lanzará la instancia.

## Flujo de trabajo de GitHub Actions

### Descripción de los pasos

1. **Checkout Repository**: El flujo de trabajo comienza realizando un `checkout` del repositorio para acceder a los archivos del proyecto.

2. **Configure AWS Credentials**: Configura las credenciales de AWS utilizando las claves de acceso proporcionadas en los secretos de GitHub.

3. **Launch EC2 Instance**: Lanza una nueva instancia EC2 en AWS utilizando los parámetros configurados. El ID de la instancia se guarda para su uso posterior.

4. **Create Custom AMI**: Una vez que la instancia EC2 está en funcionamiento, se crea una AMI personalizada utilizando la instancia recién lanzada. El nombre de la AMI incluye la fecha y hora de creación.
