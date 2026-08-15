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
## DLT STREAM

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


![image](https://github.com/user-attachments/assets/bff5c253-2f96-4e4b-9e54-24d4b0cc24cc)

____________________________________________________________________________________________________________________________________________________________________________________________________________________________

**DLT MATERIALIZED VIEW**

# Create Materialized View

@dlt.table(
    name = "first_mat_view"
)

def first_mat_view():
    
    df= spark.read.table("dltallgoher.source.orders")
    return df


![image](https://github.com/user-attachments/assets/0e357d13-73f2-4101-93fb-0f1ea92f7b5a)


Ahora crearemos dos tipos de vistas una en batch y otra en stream.

Código:

        # Create Batch View

        @dlt.view(
            name = "first_batch_view"
        )

        def first_batch_view():
    
            df= spark.read.table("dltallgoher.source.orders")
            return df

        # Create Streaming View
        @dlt.view(
            name = "first_stream_view"
        )

        def first_stream_view():
    
            df= spark.readStream.table("dltallgoher.source.orders") 
            return df


![image](https://github.com/user-attachments/assets/26bc7d6e-69d5-45d7-b7ca-5bbf6e2a5deb)

![image](https://github.com/user-attachments/assets/c04b6984-77de-49cd-b6c1-9435a89a2361)

Renombramos el cuaderno de StreamTable a Core_Components.

![image](https://github.com/user-attachments/assets/67d89382-8b39-4124-94ba-76bc3847acbe)

Ahora creamos un nuevo archivo dependencia.

![image](https://github.com/user-attachments/assets/85fbff9e-8962-436b-918a-34e7eeeeeae1)

Luego en Core_Components ejecutamos el pipeline y obtenemos lo siguiente.

![image](https://github.com/user-attachments/assets/6ccfb8cc-a96f-471e-9da5-2ce5210c5e08)

![image](https://github.com/user-attachments/assets/dcae3893-dff0-40ac-9bd0-2e02611a8cab)

Volvemos a SQL Editor y, agregamos más datos.

Código:

        --Inserting more data
        INSERT INTO orders
        VALUES (6, '2023-01-06', 106, 'shipped'),
               (7, '2023-01-07', 107, 'processing');


![image](https://github.com/user-attachments/assets/4dcd4db7-0d9e-42ef-9cb7-304c18f19609)

Seleccionamos solo lo que agregamos y ejecutamos.

![image](https://github.com/user-attachments/assets/bf555d15-7921-4497-be0e-6721d1276114)

Luego volvemos al cuderno de core_components y ejecutamos el pipeline nuevamente.

![image](https://github.com/user-attachments/assets/7123554b-38b1-41d3-92f7-04ea395f35ea)

Y ahora vemos un incremento de 2 elementos en first_mat_view, que paso de 5 a 7 y, en frist_stream_table de 1 a 2.

![image](https://github.com/user-attachments/assets/00ad533c-6a71-4afd-8ebe-c9273e0d1939)

![image](https://github.com/user-attachments/assets/8357c686-bbc9-4504-841d-1091f1be2292)

En el cuaderno dependencia. Pasamos el siguiente código.

Código:

        import dlt

        #Creating End To End Basic Pipeline

        # Staging Area
        @dlt.table(
            name = "staging_orders"
        )

        def staging_orders():
    
            df = spark.readStream.table("dltallgoher.source.orders")
            return df


y ejecutamos el código en seco (Dry Run)


![image](https://github.com/user-attachments/assets/eb15180a-7ac4-4a59-90c8-78285e94568c)


Ahora pasamos el siguiente código.

Código:

        # Creating Transformed Area
        @dlt.view(
            name = "transformed_orders"
        )

        def transformed_orders():
    
             df = spark.readStream.table("staging_orders")
             return df

y ejecutamos en seco y, veremos un tipo de dependencia o Linaje.


![image](https://github.com/user-attachments/assets/5b9e8cc5-5c40-47f0-a8eb-e2ad761d5746)

Abrimos un nuevo cuaderno exploratorio y pasamos el siguiente código.

Código:

        df = spark.read.table("dltallgoher.source.orders")
        display(df)


![image](https://github.com/user-attachments/assets/f853b69d-b087-4118-976d-c84db69aca39)

Luego hacemos las modificaciones a los siguiente códigos y ejecutamos en seco ( RunDry).

Código:

        import dlt
        from pyspark.sql.functions import lower, col

        # Creating Transformed Area
        @dlt.view(
            name = "transformed_orders"
        )

        def transformed_orders():
    
            df = spark.readStream.table("staging_orders")
            df = df.withColumn("order_status", lower(col('order_status')))
            return df

        # Creating Aggregated Area
        @dlt.table(
            name = "aggregated_orders"
        )

        def aggregated_orders():
    
            df = spark.readStream.table("transformed_orders")
            df = df.groupBy("order_status").count()
            return df


![image](https://github.com/user-attachments/assets/6a9fa05b-6618-4d0e-b5a0-545612a1c59e)

Ejecutamos y obtenemos el siguiente Linaje.

![image](https://github.com/user-attachments/assets/25cf132a-0496-463c-af8f-29c4126f6685)

![image](https://github.com/user-attachments/assets/7b4894fd-590e-459f-9509-8cdf36d384b8)

![image](https://github.com/user-attachments/assets/1546f439-9d4f-4ddf-bb11-e04ed2dc81b9)

Ahora nos vamos a workspace y seleccionamos Declarative Pipeline.

![image](https://github.com/user-attachments/assets/719be6db-c990-4eb0-8605-ab417f1ae712)

Luego creamos un query y lo renombramos DHW_source.

![image](https://github.com/user-attachments/assets/752ddaa6-1217-4b24-b2b8-0815e62d5bf1)

![image](https://github.com/user-attachments/assets/f1a125af-be81-4d35-92e0-5f8a7eea9d6d)

Ahora cargamos el siguiente código y ejecutamos.

Código:

        CREATE TABLE sales_east (
            sales_id INT PRIMARY KEY,
            customer_id INT,
            product_id INT,
            quantity INT,
            amount DECIMAL(10,2),
            sale_timestamp TIMESTAMP
        );

         -- Initial Load
        INSERT INTO sales_east VALUES
        (1, 101, 201, 2, 200.00, '2025-08-01 10:00:00'),
        (2, 102, 202, 1, 120.00, '2025-08-01 10:05:00'),
        (3, 103, 203, 5, 500.00, '2025-08-01 10:10:00'),
        (4, 104, 204, 3, 330.00, '2025-08-01 10:15:00'),
        (5, 105, 205, 4, 440.00, '2025-08-01 10:20:00');


![image](https://github.com/user-attachments/assets/eb193201-8ce9-4c78-8fb9-07eb7b2b7ec5)

Luego pasamos el siguiente código y ejecutamos.

Código:

        CREATE TABLE sales_west (
            sales_id INT PRIMARY KEY,
            customer_id INT,
            product_id INT,
            quantity INT,
            amount DECIMAL(10,2),
            sale_timestamp TIMESTAMP
        );

        -- Initial Load
        INSERT INTO sales_west VALUES
        (8, 107, 207, 1, 150.00, '2025-08-01 11:00:00'),
        (9, 108, 208, 2, 260.00, '2025-08-01 11:05:00'),
        (10, 109, 209, 3, 390.00, '2025-08-01 11:10:00'),
        (11, 110, 210, 1, 130.00, '2025-08-01 11:15:00'),
        (12, 111, 211, 4, 560.00, '2025-08-01 11:20:00');


![image](https://github.com/user-attachments/assets/cbdcbfcf-1ea0-44ff-8863-5f99fbc6b693)

Creamos la tabla de productos.

Código:

  CREATE TABLE products (
      product_id INT PRIMARY KEY,
      product_name VARCHAR(100),
      category VARCHAR(50),
      price DECIMAL(10,2),
      last_updated TIMESTAMP
  );

  -- Initial Load
  INSERT INTO products VALUES
  (201, 'Laptop', 'Electronics', 1000.00, '2025-07-31 12:00:00'),
  (202, 'Phone', 'Electronics', 120.00, '2025-07-31 12:05:00'),
  (203, 'Monitor', 'Electronics', 100.00, '2025-07-31 12:10:00'),
  (204, 'Chair', 'Furniture', 110.00, '2025-07-31 12:15:00'),
  (205, 'Desk', 'Furniture', 150.00, '2025-07-31 12:20:00'),
  (206, 'Mouse', 'Electronics', 50.00, '2025-07-31 12:25:00'),
  (207, 'Keyboard', 'Electronics', 60.00, '2025-07-31 12:30:00'),
  (208, 'Lamp', 'Furniture', 130.00, '2025-07-31 12:35:00'),
  (209, 'Router', 'Electronics', 130.00, '2025-07-31 12:40:00'),
  (210, 'Table', 'Furniture', 130.00, '2025-07-31 12:45:00'),
  (211, 'Notebook', 'Stationery', 140.00, '2025-07-31 12:50:00'),
  (212, 'Pen', 'Stationery', 150.00, '2025-07-31 12:55:00');


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
