# Práctica de AWS X-Ray adaptada para sandbox de AWS Academy Learner Labs

## PASO 1
Crear un bucket en S3 en la región us-east-1 donde se almacenará el paquete de despliegue de la aplicación

  > $ aws s3 mb s3://<nombre_bucket>

## PASO 2
Utilizar la plantilla original de AWS CloudFormation suministrada como plantilla.yml e introducir la orden para subir el paquete de despliegue y generar la plantilla de salida:

  > $ aws cloudformation package --s3-bucket <nombre_bucket> --template-file plantilla.yml --output-template-file salida.yml --region us-east-1

## PASO 3
Utilizar la plantilla generada en el paso anterior, salida.yml para desplegar la infraestructura necesaria y la aplicación

  > $ aws cloudformation deploy --template-file salida.yml --stack-name mi-aplicacion --capabilities CAPABILITY_IAM --region us-east-1