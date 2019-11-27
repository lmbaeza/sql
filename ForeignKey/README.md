# Foreign Key

La clave externa o FOREIGN KEY, es una columna o varias columnas, que sirven para señalar cual es la clave primaria de otra tabla.

## Codigo SQL en PostgreSQL

```sql
DROP TABLE IF EXISTS "DB_Name"."public"."carrera";
DROP TABLE IF EXISTS "DB_Name"."public"."facultad";


CREATE TABLE IF NOT EXISTS "DB_Name"."public"."facultad" (
    "facultad_id"            SERIAL        NOT NULL,
    "nombre_facultad"        VARCHAR(100)  NOT NULL,
    PRIMARY KEY ("facultad_id")
);


CREATE TABLE IF NOT EXISTS "DB_Name"."public"."carrera" (
    "carrera_id"         SERIAL         NOT NULL,
    "nombre_carrera"     VARCHAR(100)   NOT NULL,
    "facultad_id"        INT            NOT NULL,
    CONSTRAINT "fk_facultad_id"
        FOREIGN KEY ("facultad_id")
            REFERENCES "DB_Name"."public"."facultad" ("facultad_id")
            ON DELETE NO ACTION
            ON UPDATE NO ACTION,
    PRIMARY KEY ("carrera_id")
);

CREATE INDEX "index_facultad_id" ON "DB_Name"."public"."facultad" ("facultad_id" ASC);
CREATE INDEX "index_carrera_id" ON "DB_Name"."public"."carrera" ("carrera_id" ASC);
```