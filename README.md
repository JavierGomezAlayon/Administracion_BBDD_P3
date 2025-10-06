
## Explicación de las entidades
En este apartado se recoge una breve descripción de las entidades definidas y además el rango y ejemplos de sus atributos.  
Los atributos tendrán entre paréntesis el tipo de variable que es, después una breve descripción y un ejemplo, todo separado por el carácter ":".

- **Cliente**
  - Código (secuencial): Identificador único del cliente. : 1
  - Crédito (bool): Si el cliente tiene crédito. : true
    - **Cliente Plus**: Cliente con ventajas adicionales.
    - **Cliente normal**: Cliente estándar.
- **Vivero**
  - IDV (secuencial): Identificador del vivero. : 1
  - Nombre (varchar): Nombre del vivero. : "Vivero San Telmo"
  - Georreferencia (Object): Contiene la posición del vivero
    - Latitud (decimal): El grado de latitud de la coordenada: 3.7038
    - Longitud (decimal): El grado de longitud de la coordenada: 4.6788
- **Zona**
  - IDZ (secuencial): Identificador de la zona. : 1
  - Nombre (varchar): Nombre de la zona de la tienda. : "Almacen"
  - Georreferencia (Object): Contiene la posición de la zona
    - Latitud (decimal): El grado de latitud de la coordenada: 2.5638
    - Longitud (decimal): El grado de longitud de la coordenada: 4.6213
- **Producto**
  - IDP (secuencial): Identificador del producto. : 1
  - Nombre (varchar): Nombre del producto. : "Amapola"
  - Precio (decimal): Precio de venta. : 15.5
- **Empleado**
  - DNI (varchar): Documento Nacional de Identidad. : "12345678A"
  - Nombre (varchar): Nombre del empleado. : Javier
- **Periodo**
  - ID (secuencial): Identificador del periodo. : 1
  - Fecha Inicio (date): Fecha de inicio del periodo. : "2025-01-01"
  - Fecha Fin (date): Fecha de fin del periodo. : "2025-12-31"

## Explicación de las relaciones
Aquí se explican las relaciones definidas.  
Al final de la descripción se pondrá el ((min,max) de la primera entidad, cardinalidad de la relación, (min,max) de la segunda entidad).

- **Compra**: Uno o varios *Clientes* realizan una **Compra** de uno o varios *Productos* en una *Fecha* determinada. (1,N) : (N,M) : (1,M)
  - Fecha (date): Fecha de la compra. : "2025-09-01"
  - Número (integer): Cantidad de productos comprados. : 6
- **Producto en**: Uno o varios *Productos* **Están** en una *Zona*. (1,1) : (1,N) : (1,N)
  - Cantidad (integer): Número de productos almacenados. : 20
- **Empleado en**: Un *Empleado* **Trabaja** en una *Zona* y *rango* temporal determinado. (1,N) : (N,M) : (1,M)
  - Periodo (Objeto) : Periodo en el que el empleado a estado en cierta zona.
    - Fecha inicio : Fecha de inicio del rango : "2025-01-05"
    - Fecha finalización : Fecha de finalización del rango : "2025-03-05"
- **Tiene**: Un *Vivero* **Tiene** una o varias *Zonas*. (1,1) : (1,N) : (1,N)
- **Pedido**: Uno o varios *clientes* **piden** uno o varios *productos* y el pedido es gestionado por un *empleado* (1,N) : (1,M) : (1,1)
