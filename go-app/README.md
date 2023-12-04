# Uso de este repositorio

**Hay 2 dockerfile**
    Dockerfile-1 : sin estructura
    Dockerfile-2 : con estructura


# Que es multi-stage

Es una forma de escribir un dockerfile pero con varias etapas internamente en este dockerfile. Esto se hace con el fin de optimizar el peso final de la imagen para despligue mas rapidos 

## Ventajas de multi-stage

**La mayor ventaja este en 2 arias:**
  - Seguridad   
  - Reducion de tamaño de la imagen final 

## Forma de hacer un dockerfile multi-stage

Generalmente son 2 etapas pero internamente se puede escribir las etapas que quieras:

**1)Indentificar las etapas**
  - 1.1)Si la etapa no tiene ningun identificador empieza por 0 
from=0
  - 1.2)Identificador por tag se puede agregar un tag luego del from 
from nginx As (tag)

**2)Copiar de 1 etapa a otra lo que necesito**
  - Luego copiar el resultado de la etapa anterior , para copiarlo se usa el tag de la etapa anterior y la linea
COPY --from=tag 


#Estructura go

Go no tiene un estructura definida pero la estructura mas comun es la siguiente:

![Diagrama](https://github.com/Andherson333333/Docker/blob/main/go-app/go.JPG)

