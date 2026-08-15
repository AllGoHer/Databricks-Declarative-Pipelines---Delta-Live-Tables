# Databricks-Declarative-Pipelines---Delta-Live-Tables
________________________________________________________________________________________________________________________________________________________________________________________________________________

1.	Creamos un catálogo ejem. dltallgoher y configuramos.

![image](https://github.com/user-attachments/assets/9cc6a0cc-b4c8-417d-8f40-6aa4c2576f9f)

![image](https://github.com/user-attachments/assets/7de2383c-6d5b-4de5-938a-7b6f556ae8e1)

![image](https://github.com/user-attachments/assets/97cd2830-9e4e-417b-9586-0b4b254bab7b)

![image](https://github.com/user-attachments/assets/c39025e7-649f-4074-89a9-ccd1e2650e89)

![image](https://github.com/user-attachments/assets/6c009e94-2c71-46f3-b886-391c99a1c288)

![image](https://github.com/user-attachments/assets/607b6351-7faf-46be-89cc-79d55dbadc76)

* Luego creamos un nuevo espacio de trabajo.
  
![image](https://github.com/user-attachments/assets/2cc8215a-60db-49c3-ad85-caf52c934adb)

![image](https://github.com/user-attachments/assets/3fabd3f8-9243-4f4d-9582-dee1a07aa0a7)

![image](https://github.com/user-attachments/assets/e2081abc-b1ae-4d62-9f1c-6764d652cdb7)

Ahora volvemos a catalogo hacemos click en nuestro catalogo (dtlallgoher) y luego en crear esquema llamado source.

![image](https://github.com/user-attachments/assets/972067bc-6662-4a40-a6fe-70933337c4a3)

![image](https://github.com/user-attachments/assets/e5f909fc-eade-4cdb-a0f4-e4d7603daa3f)

![image](https://github.com/user-attachments/assets/f4e67f62-aaad-43ce-9f47-6aff7ed4ccae)

* Ahora crearemos una tabla

![image](https://github.com/user-attachments/assets/a83987a8-ccbe-45ca-a490-12a9270dc440)

Vamos a sql editor y cambiamos el nombre del New Query Editor por source_orders

![image](https://github.com/user-attachments/assets/ceebe53e-6ed4-4842-ab44-d1ecb84ff448)

![image](https://github.com/user-attachments/assets/dc6a4bc6-5385-4445-b1c5-112ef9645a11)

Primero hacemos click en workspace y seleccionamos dtlallgoher.

![image](https://github.com/user-attachments/assets/de2fbeec-0bf5-4b13-b1b9-8445a628bb58)

Ahora seleccionamos el esquema haciendo click en schema y elegimos source.

![image](https://github.com/user-attachments/assets/985c06cf-934c-40e4-a8ab-a246295d61e5)

Ahora escribimos el siguiente código.

SQL:

     CREATE TABLE orders
     (
         order_id INT,
         order_date DATE,
         customer_id INT,
         order_status STRING
     );

     INSERT INTO orders
     VALUES (1, '2023-01-01', 101, 'shipped'),
            (2, '2023-01-02', 102, 'processing'),
            (3, '2023-01-03', 103, 'shipped'),
            (4, '2023-01-04', 104, 'shipped');

Luego damos correr (Run all)


![image](https://github.com/user-attachments/assets/34ad4b8a-c196-42bc-882f-4d5699691ab1)

Sql:

        SELECT * FROM orders;


![image](https://github.com/user-attachments/assets/0b5b79aa-fd44-424d-970e-ac5da63fb531)

Ahora moveremos el cuaderno (notebook) al archivo o espacio de trabajo que creamos al comienzo (Declarative Pipeline).

1.	Hacemos click en el icono de la carpeta y en la ventana desplegable seleccionamos source_orders.
   
2.	En la ventana emergente hacemos click en move.
   
3.	En la ventana emergente hacemos click en Declarative Pipeline y luego en move.


![image](https://github.com/user-attachments/assets/30e91b0a-04d4-4972-a262-5e3c9912eb0e)

![image](https://github.com/user-attachments/assets/de543793-1a60-4427-925f-30592e47b07e)

Luego hacemos click en move

![image](https://github.com/user-attachments/assets/6ce2a1f4-6d90-4c04-b05c-9cc7c82c9e97)

Luego nos vamos a workspace y seleccionamos declarative pipeline

![image](https://github.com/user-attachments/assets/ae0283e3-e67a-4ce8-9836-a8e952d6b92a)

Ahora creamos una nueva carpeta DTL.

![image](https://github.com/user-attachments/assets/751dadb0-0a18-4397-ba84-9b9f37e24ef1)

![image](https://github.com/user-attachments/assets/0c543c41-a1a7-4376-bc2e-d59a4c84028e)

Ahora nos vamos a JOB & PIPELINES, luego hacemos click en crear y seleccionamos ETL pipeline.

![image](https://github.com/user-attachments/assets/5ec087c4-2ab5-4afa-b3ce-4eaf20e471ea)

![image](https://github.com/user-attachments/assets/72dfbf54-8268-4cdd-9e15-e9aace57571b)

Luego hacemos click en workspace y seleccionamos dtlallgoher.

![image](https://github.com/user-attachments/assets/e3296669-00c8-4d29-b3c6-9496aa70c5ef)

Y en esquema seleccionamos crear esquema (+ Create schema)

![image](https://github.com/user-attachments/assets/4c54ef2c-123d-4b27-8c2a-42c9b01828c8)

Luego le asignamos el nombre de dtl_schema

![image](https://github.com/user-attachments/assets/e0a41aa2-8fae-431d-aa23-e3f94687ed01)

Luego guardar.

![image](https://github.com/user-attachments/assets/0aa3aa8c-b689-43d3-8ad4-0cd928e3e052)

![image](https://github.com/user-attachments/assets/ccc15c7f-f316-45ca-a329-14ae0d72ca04)

Ahora movemos el NEW PIPELINE a la carpeta de trabajo.

![image](https://github.com/user-attachments/assets/55e2c2d3-0e85-4f84-b0b7-be0fa6fd9744)

Luego en la ventana emergente hacemos click en FOR YOU y seleccionamos DLT nuestra carpeta de trabajo que creamos anteriormente.

![image](https://github.com/user-attachments/assets/f50efbe8-1540-4fbf-9b30-5fa37cdf7e7b)

Y por último, hacemos click en move.

![image](https://github.com/user-attachments/assets/6c1b148f-0035-4a70-8a95-b7d6f24b991e)

Ahora hacemos click en la ventana pipeline

![image](https://github.com/user-attachments/assets/4dbffbb5-118b-4b20-bb4f-5fc63fb46f94)

Luego hacemos click en los tres puntitos de la carpeta New Pipeline 2026-07-29 y, en la ventana emergente hacemos click en Rename root folder.

![image](https://github.com/user-attachments/assets/38962134-48bb-49e4-bb3c-eb110d06eeee)

![image](https://github.com/user-attachments/assets/677d63f1-3c2e-48ec-9835-ca48e648661f)

Ahora cambiamos el nombre de la canalización por DLT_Tutorial

![image](https://github.com/user-attachments/assets/4228c98d-b531-46a6-8f04-10d2448ad0a1)

![image](https://github.com/user-attachments/assets/9c3a0ba5-622d-43fb-9ea5-46d2454ab5fe)

Luego renombramos el archivo transformations por transformations_SourceCode.

![image](https://github.com/user-attachments/assets/d8b79cfd-77a8-48c9-8980-1b2160c23c7d)

![image](https://github.com/user-attachments/assets/1ddefd1a-c409-4732-82f2-c88c0c85838b)

Y también, creamos la carpeta demo dentro de transformations_SourceCode.

![image](https://github.com/user-attachments/assets/9acb7a3d-4d07-407b-b52d-7e37acb4a7ff)

Ahora creamos dentro del archivo demo un file llamado 1_StreamTable (el file se crea automatico, luego será renombrado)


![image](https://github.com/user-attachments/assets/e19ba989-b02d-4889-806e-1c4f97473be1)

________________________________________________________________________________________________________________________________________________________________________________________________________________
DLT STREAM

Ahora ejecutamos el siguiente código de python decorativo de forma seca (Dry Run)


Código:


        import dlt

        # Creating Stream table

        @dlt.table(
            name = "first_stream_table"
        )

        def first_stream_table():
    
            df= spark.readStream.table("dltallgoher.source.orders")
            return df


![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()

![image]()
