# Informe de Refactorización: TechNova Cloud v2.0

## 1. Introducción
Este proyecto presenta la evolución del esquema `CatalogoCloud.xsd` y su correspondiente `CatalogoCloud.xml`, aplicando técnicas  y validación xsd para un entorno de infraestructura Cloud.

## 2.Respuestas del Reto

### a. ¿Cuántas líneas de código habéis ahorrado al usar grupos?
Al implementar `xs:attributeGroup` para los atributos básicos del servidor (id, rack, estado) y `xs:group` para el bloque de hardware, se han ahorrado aproximadamente 12 líneas de código por cada declaración de servidor en el esquema. 

En lugar de definir toda la estructura interna cada vez, ahora simplemente llamamos a los grupos mediante una sola línea lo que hace que el código sea mucho más limpio, profesional y fácil de mantener de cara a futuras ampliaciones del catálogo.

### b. ¿Qué error os da VS Code si intentáis poner dos servidores con el mismo ID?
Al intentar duplicar un atributo `@id` en dos servidores distintos, Visual Studio Code muestra un error de validación de Restricción de Identidad (Identity Constraint 

El mensaje de error indica que existe un valor duplicado para la restricción de identidad, esto confirma que el validador impide que existan dos servidores con el mismo identificador garantizando la integridad de la base de datos de la infraestructura
