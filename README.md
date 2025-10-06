# Administracion_BBDD_P3

## Explicación de las entidades
En este apartado se recoge una breve descripción de las entidades definidas y además el rango y ejemplos de sus atributos
Los atributos tendrá entre parentesis el tipo de variable que es y después se le indica una breve descripción y un ejemplo, todo separado por el caracter ":".
- **Cliente**: Persona que haya realizado al menos una compra.
  - Código (secuencial):
  - Crédito (bool): Indica si el cliente es con crédito o no. : true
    - **Cliente Plus**: persona que tiene el plan Tajinaste Plus. 
    - **Cliente normal**: persona que ha realizado una compra. 
- **Vivero**: Sitio donde se pueden comprar diferentes productos de TajinasteSA 
  - IDV (secuencial): Atributo identificativo que consiste en un código serial. : 3891
- **Zona**: Las zonas diferenciadas dentro del vivero. 
  - IDZ (secuencial): Atributo identificativo que consiste en un código serial. : 0001
- **Producto**: todos los productos que se vende en la compañia. 
  - IDP (secuencial): Atributo identificativo que consiste en un código serial. : 1003
  - Nombre (varchar): Nombre del producto. :Amapola
  - Precio (Number): Precio de compra del medicamento. : 15,5
- **Trabajador**: Personal que está trabajando en cualquiera de las zonas de los viveros de la empresa. 
  - DNI (varchar) : Atributo identificativo que consiste en un código serial. : 46826481A
  
## Explicación de las relaciones
Aquí se explica las relaciones definidas.
Al final de la descripción se pondrá el ((min,max) de la primera entidad, Cardinal de la relación, (min,max) de la segunda entidad)
- **Compra**: Un *Cliente* **Compra** un número de *Productos* en una fecha.  (1,N) : (N,M) : (1,M)
  - Fecha compra (Date): Fecha en la que se realiza la compra. : 01/09/25
  - Número (Integer): Número de *Medicamentos* que compra el *Cliente*. : 6
  - Fecha pago (Date): Fecha en la que se realizará el pago de la compra. : 12/09/25 (solo si el comprador es un cliente con crédito)
- **Almacena**: Algún o ningún *Medicamento* se **Almacena** en una o varias *Farmacia*.  (0,N) : (N,M) : (1,M)
  - Reserva (Integer): Número de *Medicamentos* que se almacenan en la *Farmacia*. : 20
- **Fabricación**: Algún o ningún *Medicamento* es **Fabricado** en alguna o ninguna *Farmacia*. (0,N) : (N,M) : (1,M)
- **Obtención**: Alguna o ningúna *Farmacia* **Obtiene** medicamentos fabricados por algún o varios *Laboratorios*. (0,N) : (N,M) : (0,M)
  - Cantidad (Integer): Cantidad de *Medicamentos* dados por el *Laboratorio*. : 25
- **Pertenece**: Un o varios *Medicamentos* **Pertenecen** a una o varias *Familias*. (1,N) : (N,M) : (1,M)
