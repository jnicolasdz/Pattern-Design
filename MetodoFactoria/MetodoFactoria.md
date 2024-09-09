# Método Factoria 

El metodo factoria nos permite ampliar generar objetos de clases concretas ya existentes, haciendo las variaciones que requiramos sin necesidad de modificar el codigo existente ni de alterar las dependencias.
## Proposito:

Durante el inicio de un desarollo o al pensar en su mantenimiento y extension es comun desconocer el alcance que tendra un programa y los requerimientos que tendra a futuro, pensando en un futuro que puede ser tanto en el despliegue como en el desarollo. El patron Fabrica permite generar una estructura sencilla de plasmar al principio del desarollo y cumpliendo los principios:
- Responsabilidad unica.
- Abierto a la extension, cerrado a la modificacion.

## Problema

Imaginemos que tenemos una clase concreta A, despues requerir una variacion de esta clase, llamada clase concreta B. ¿Tendriamos que reescribir el codigo? No, para eso podemos heredar, haciendo B hija de A. ¿Si necesitamos una clase C similar a B? Heredamos B en C.
¿Podemos repetir este truco hasta el infinito?

[diagrama de clases del caso anterior]

Si tenemos una clase N que se asemeja a la clase A pero comparte atributos con la clase B y a su vez tiene metodos de la clase C.
¿Multiples heredacion? No, nuestro programa se ha complicado exponencialmente con cada clase que agregamos, debe haber una mejor solucion.

[Diagrama aplicando una clase abstracta]

Quien ya haya trabajo a profunidad programacion orientada a objetos (POO), pudo pensar en esta solucion, generar una clase abstracta que contenga los atributos y metodos más genericos y generar todas las clases concretas como implementacion de la clase abstracta, dejando sus modificaciones bajo el principio del polimorfismo.

Esta solucion es buena pero ahora añadamos un cliente, este cliente requerira acceder a todas, una o un grupo de estas clases dependiendo de sus necesidades. Con nuestro modelo actual tendriamos lo siguiente:

[Diagrama anterior aplicando un cliente]

Nuevamente nuestro sistema se ha complicado ya que el cliente debera tener un metodo capaz de definir que momento utilizar cada clase; resumiendo en una sucesion de condicionales y restringiendo al cliente a un o a un grupo de clases concretas.

## Solucion 

Crear una clase fabrica que sea su trabajo sea generar los objetos de las clases concretas, de esta forma cualquier cliente podra acceder a la fabrica para la creacion de un objeto. Ademas se puede expandir a que esta clase fabrica sea abstracta, es decir, que sus metodos y atributos esten declarados pero no definidos, asi se da la flexibilidad para que cada clase concreta que la implemente defina los metodos como requiera usarlos.

- Cumple la responsabilidad unica al dejar a la fabrica el trabajo explicito de generar los objetos de un tipo de dato

- Cumple abierto a la extension, cerrado a la modificacion; la adicion de una nueva clase concreta solo requiere de su referencia dentro de la clase fabrica. 

[Diagrama aplicando patron fabrica]

## Definicion

La junta de Andalucia define el patron como: Centraliza en una clase constructora la creación de objetos de un subtipo de un tipo determinado, ocultando al usuario la casuística para elegir el subtipo que crear.

## Aplicacion 
Aplicaquemos este patron a un programa que genera distinto tipo de documentos de identificacion: 

[Diagrama de clases usando como ejemplo documentos]

Falta agregar ejemplo en codigo