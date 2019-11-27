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

**NUMERIC:**

El tipo numérico puede almacenar números con hasta 1000 dígitos de precisión y realizar cálculos exactamente. Se recomienda especialmente para almacenar cantidades monetarias y otras cantidades donde se requiere exactitud. Sin embargo, la aritmética en valores numéricos es muy lenta en comparación con los tipos enteros o con los tipos de punto flotante descritos en la siguiente sección.

Utilizamos los siguientes términos a continuación: La escala de un numérico es el número de dígitos decimales en la parte fraccionaria, a la derecha del punto decimal. La precisión de un numérico es el número total de dígitos significativos en el número entero, es decir, el número de dígitos a ambos lados de la coma decimal. Entonces el número 23.5141 tiene una precisión de 6 y una escala de 4. Se puede considerar que los enteros tienen una escala de cero.

Se pueden configurar tanto la precisión máxima como la escala máxima de una columna numérica . Para declarar una columna de tipo numérico, use la sintaxis:

`NUMERIC(precision, scale)` La precisión debe ser positiva, la escala cero o positiva. Alternativamente:

`NUMERIC(precision)` selecciona una escala de 0. Especificando:

 `NUMERIC` sin ninguna precisión o escala, se crea una columna en la que se pueden almacenar valores numéricos de cualquier precisión y escala, hasta el límite de implementación de precisión. Una columna de este tipo no obligará a los valores de entrada a ninguna escala en particular, mientras que las columnas numéricas con una escala declarada obligarán a los valores de entrada a esa escala. (El estándar SQL requiere una escala predeterminada de 0, es decir, coerción a la precisión entera. Nos parece un poco inútil. Si le preocupa la portabilidad, siempre especifique la precisión y la escala explícitamente).


# Bibliografia
[[1]](https://www.postgresql.org/docs/9.0/datatype-numeric.html) Postgresql.org. (2019). PostgreSQL: Documentation: 9.0: Numeric Types. [online] Available at: https://www.postgresql.org/docs/9.0/datatype-numeric.html.