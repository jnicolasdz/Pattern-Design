# Factoria Abstracta

La factoria abstracta nos permite generalizar la produccion de objetos similares bajo una
misma interfaz o clase abstracta, de forma que podemos tener objetos distintos relacionados
bajo la misma fabrica.

## Proposito

Generar un desacoplamiento entre las fabricas concretas de objetos similares por medio de la creacion de una fabrica abstracta cuya funcion sea la creacion de fabricas capaces de generar familias de objetos. De esta forma se garantiza una la creacion de varios objetos a la vez sin la necesidad de conocer su implementacion concreta.

## Problema 