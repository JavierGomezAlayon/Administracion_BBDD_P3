
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
- **Zona**
  - IDZ (secuencial): Identificador de la zona. : 1
- **Producto**
  - IDP (secuencial): Identificador del producto. : 1
  - Nombre (varchar): Nombre del producto. : "Amapola"
  - Precio (decimal): Precio de venta. : 15.5
- **Trabajador**
  - DNI (varchar): Documento Nacional de Identidad. : "12345678A"
- **Tienda**
  - IDT (secuencial): Identificador de la tienda. : 1
  - Nombre (varchar): Nombre de la tienda. : "Tienda Central"
- **Periodo**
  - ID (secuencial): Identificador del periodo. : 1
  - Fecha Inicio (date): Fecha de inicio del periodo. : "2025-01-01"
  - Fecha Fin (date): Fecha de fin del periodo. : "2025-12-31"
- **ProductoVividal**
  - ID (secuencial): Identificador del producto vividial. : 1
- **Productividad**
  - ID (secuencial): Identificador de la productividad. : 1
- **Longitud**
  - ID (secuencial): Identificador de la longitud. : 1
- **Latitud**
  - ID (secuencial): Identificador de la latitud. : 1

## Explicación de las relaciones
Aquí se explican las relaciones definidas.  
Al final de la descripción se pondrá el ((min,max) de la primera entidad, cardinalidad de la relación, (min,max) de la segunda entidad).

- **Compra**: Un *Cliente* realiza una **Compra** de uno o varios *Productos* en una *Tienda* y en una *Fecha* determinada. (1,N) : (N,M) : (1,M)
  - Fecha (date): Fecha de la compra. : "2025-09-01"
  - Número (int): Cantidad de productos comprados. : 6
- **Almacena**: Un *Producto* se **Almacena** en una *Tienda* en un *Periodo* específico. (0,N) : (N,M) : (1,M)
  - Reserva (int): Número de productos almacenados. : 20
- **Trabaja**: Un *Trabajador* **Trabaja** en una *Tienda*. (1,N) : (N,M) : (1,M)
- **Situada**: Una *Tienda* está **Situada** en una *Zona*. (1,N) : (N,M) : (1,M)
- **Ubicación**: Una *Zona* tiene una **Ubicación** (Longitud y Latitud). (1,1) : (1,1) : (1,1)
- **Productividad**: Un *Producto* tiene una **Productividad** registrada en un *Periodo*. (1,N) : (N,M) : (1,M)