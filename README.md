[![Deploy to EC2](https://github.com/amurpo/desafio2-devops/actions/workflows/ec2.yml/badge.svg)](https://github.com/amurpo/desafio2-devops/actions/workflows/ec2.yml)

# Desafío 2 - DevOps

Este es un proyecto que implementa un servidor web utilizando **Node.js** y **Express**. El código está desplegado en una instancia de **EC2** en AWS, y el tráfico HTTP es dirigido a través de un **proxy inverso Nginx**.

## Requisitos

- **Node.js 20.x**: Utilizado para ejecutar la aplicación en el servidor.
- **PM2**: Para la gestión de procesos de la aplicación.
- **Nginx**: Usado como proxy inverso para dirigir el tráfico HTTP desde el puerto 80 hacia la aplicación en el puerto 8080.
- **EC2**: La aplicación está desplegada en una instancia de Amazon EC2.
