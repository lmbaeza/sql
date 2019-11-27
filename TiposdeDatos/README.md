# Tipos de Datos en SQL

## Contenido

* Tipos de datos en PostgreSQL
    * Tipos Numericos

## PostgreSQL

#### Tipos Numericos

| Nombre         | Tamaño        | Descripción  | Rango    |
| :------------- |:-------------:| :------------| ---------: |
| smallint      | 16 Bits | Numero entero de rango pequeño | -32768 to +32767 |
| integer      | 32 Bits      |Generalmente Usado para enteros | -2147483648 to +2147483647 |
| bigint | 64 bits      | Enteros grandes | -9223372036854775808 to 9223372036854775807 |
| serial | 32 Bits | entero autoincrementable | 1 to 2147483647 |
| bigserial | 64 Bits | entero autoincrementable grande | 1 to 9223372036854775807 |
| real | 32 Bits | precisión variable, inexacta | 	6 digitos decimales de precisión |
| double precision | 64 Bits  | precisión variable, inexacta | 15 digitos decimales de precisión |
| decimal | variable | precisión especificada por el usuario, exacta | Sin Limite |
| numeric | variable | precisión especificada por el usuario, exacta | Sin Limite |

# Bibliografia
[[1]](https://www.postgresql.org/docs/9.0/datatype-numeric.html) Postgresql.org. (2019). PostgreSQL: Documentation: 9.0: Numeric Types. [online] Available at: https://www.postgresql.org/docs/9.0/datatype-numeric.html.