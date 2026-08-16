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

Código:

        ## Create Materialized View

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


![image](https://github.com/user-attachments/assets/1db84775-fb18-4e20-b9a5-f65e10e5cdcf)

Luego creamos la tabla de clientes.

Código:

        CREATE TABLE customers (
            customer_id INT PRIMARY KEY,
            customer_name VARCHAR(100),
            region VARCHAR(50),
            last_updated TIMESTAMP
        );


        -- Initial Load
        INSERT INTO customers VALUES
        (101, 'Alice', 'East', '2025-07-31 13:00:00'),
        (102, 'Bob', 'East', '2025-07-31 13:05:00'),
        (103, 'Charlie', 'East', '2025-07-31 13:10:00'),
        (104, 'Diana', 'East', '2025-07-31 13:15:00'),
        (105, 'Ethan', 'East', '2025-07-31 13:20:00'),
        (106, 'Fiona', 'East', '2025-07-31 13:25:00'),
        (107, 'George', 'West', '2025-07-31 13:30:00'),
        (108, 'Hannah', 'West', '2025-07-31 13:35:00'),
        (109, 'Ian', 'West', '2025-07-31 13:40:00'),
        (110, 'Jane', 'West', '2025-07-31 13:45:00'),
        (111, 'Kevin', 'West', '2025-07-31 13:50:00'),
        (112, 'Laura', 'West', '2025-07-31 13:55:00');



![image](https://github.com/user-attachments/assets/b070745a-ee26-47eb-9e67-8d76e576377b)


___________________________________________________________________________________________________________________________________________________________________________________________________________________________
## CREACIÓN DE ARQUITECTURA MEDALLÓN

Nos vamos ahora a al workspace al icono de carpeta y hacemos click en los tres puntos de transformations_SourceCode y, en la ventana emergente haz click en Create folder

### CAPA BRONCE

![image](https://github.com/user-attachments/assets/49b43e78-e04a-433b-8d36-4d10931a295e)

Nombraremos a esa carpeta como bronce.

![image](https://github.com/user-attachments/assets/3140ec7c-b066-4772-bad3-1eec5d6db553)

![image](https://github.com/user-attachments/assets/c22855d6-1591-4e7c-a526-2618e9442742)

Ahora creamos un archivo de ingestión de datos llamado ingestión_sales.py

![image](https://github.com/user-attachments/assets/bafa299b-9188-4e06-bc13-9e2561924049)

Código:

        import dlt

        # Empty Streaming Table
        @dlt.create_streaming_table(
            name = "append_sales"
        )

        #Create East Sales Flow
        @dlt.append_flow(target="append_sales")
        def esat_sales():

            df = spark.readStream.table("dltallgoher.source.sales_east")
            return df

        #Create West Sales Flow
        @dlt.append_flow(target="append_sales")
         def west_sales():

            df = spark.readStream.table("dltallgoher.source.sales_west")
            return df



![image](https://github.com/user-attachments/assets/b8f70af1-1ec9-4b04-8bd1-3dda405c9d94)

Ahora creamos un nuevo archivo ingestión_products.py

![image](https://github.com/user-attachments/assets/2d5b5fca-78a8-49cd-9e69-8b389a2d7b5c)

Pasamos el siguiente código:

Código:

        import dlt

        # Igestion Products
        @dlt.table(
            name = "products_stg"
        )

        def products_stg():

            df = spark.readStream.table("dltallgoher.source.products")
            return df


luego ejecutamos el código en seco.


![image](https://github.com/user-attachments/assets/21fb464c-5117-4d6f-870a-49c74590a788)

Ahora creamos el archivo de ingestión_customers.py

![image](https://github.com/user-attachments/assets/7f5fae4d-7fe8-400c-ad7a-f2a517c7f1e0)


Código:

        import dlt

        # Ingestion customers
        @dlt.table(
            name = "customers_stg"
        )

        def customers_stg():

            df = spark.readStream.table("dltallgoher.source.customerss")
            return df


![image](https://github.com/user-attachments/assets/2a0b4cd9-8e3a-4544-a338-75a726108fa2)

![image](https://github.com/user-attachments/assets/c9e75fc8-f4d4-4056-aa26-7348c9726362)

![image](https://github.com/user-attachments/assets/2d30708a-312f-484a-b71a-8ec88478cb79)

____________________________________________________________________________________________________________________________________________________________________________________________________________________________

### CREACION DE EXPECTATIVAS

Ahora vamos agregar las expectativas a los códigos, así es, que serán modificados de la siguiente manera.

**Ingestion Sales**

Código:

        import dlt

        # Sales Expectations
        sales_rules = {
            "rule_1" : "sales_id IS NOT NULL"
        }

        # Empty Streaming Table
        dlt.create_streaming_table(
            name = "sales_stg",
            expect_all_or_drop = sales_rules
        )

        #Create East Sales Flow
        @dlt.append_flow(target="sales_stg")
        def east_sales():

            df = spark.readStream.table("dltallgoher.source.sales_east")
            return df

        #Create West Sales Flow
        @dlt.append_flow(target="sales_stg")
        def west_sales():

            df = spark.readStream.table("dltallgoher.source.sales_west")
            return df


__________________________________________________________________________________________________________________________________________________

**Ingestión Products**


Código:

        import dlt

        # Products Expectations
        products_rules = {
            "rule_1" : "product_id IS NOT NULL",
            "rule_2" : "price >= 0"
            }

        # Igestion Products
        @dlt.table(
            name = "products_stg"
        )

        @dlt.expect_all(products_rules)
        def products_stg():

            df = spark.readStream.table("dltallgoher.source.products")
            return df


__________________________________________________________________________________________________________________________________

**Ingestion Customers**


Código:

        import dlt

        #Customers Expectations
        customers_rules = {
            "rule_1" : "customer_id IS NOT NULL",
            "rule_2" : "customer_name IS NOT NULL"
            }

        # Ingestion customers
        @dlt.table(
            name = "customers_stg"
        )

        @dlt.expect_all_or_drop(customers_rules)
        def customers_stg():

            df = spark.readStream.table("dltallgoher.source.customerss")
            return df

Luego corremos en seco y veremos lo siguiente.


![image](https://github.com/user-attachments/assets/c121f0f2-c656-43c4-aba2-c3934f0b3612)


Expectation:


![image](https://github.com/user-attachments/assets/34a8d17f-eeae-4ae4-9c29-e3011569dccf)

____________________________________________________________________________________________________________________________________________________________________________________________________________________________
### CAPA DE PLATA

Creamos una nueva carpeta de plata


![image](https://github.com/user-attachments/assets/5d79d2d4-7f38-43a3-ab98-dba1a55cc7e4)

![image](https://github.com/user-attachments/assets/bc66b89f-b237-4773-b030-845aadf882ad)

Ahora dentro de la capa silver creamos un archivo llamado transform_sales.py

![image](https://github.com/user-attachments/assets/2d147aaf-75bb-4ba8-a455-7da6600b6e68)

Luego, pasamos el siguiente código.

Código:

        import dlt

         # Creating Destination Silver
         dlt.create_streaming_table(
              name="sales_enr"
        )

        dlt.create_auto_cdc_flow(
          target = "sales_enr",
          source = "sales_stg",
          keys = ["sales_id"],
          sequence_by = "sale_timestamp",
          ignore_null_updates = False,
          apply_as_deletes = None,
          apply_as_truncates = None,
          column_list = None,
          except_column_list = None,
          stored_as_scd_type = 1,
          track_history_column_list = None,
          track_history_except_column_list = None
        )


![image](https://github.com/user-attachments/assets/7b111c62-088b-4a6e-98b0-d21c23307d0f)

![image](https://github.com/user-attachments/assets/7db2a4ff-29b7-44d7-a704-1a436a751281)

Ahora hacemos la transfromacion de los datos de venta.

Código:

        import dlt
        from pyspark.sql.functions import *

        # Transforming Sales Data
          @dlt.view(
            name = "sales_stg_transf"
        )

        def sales_stg_transf():
            df = spark.readStream.table("sales_stg")
            df = df.withColumn("total_amount", col("quantity") * col("amount"))
            return df
                       

        # Creating Destination Silver
         dlt.create_streaming_table(
           name="sales_enr"
        )

        dlt.create_auto_cdc_flow(
          target = "sales_enr",
          source = "sales_stg_transf",
          keys = ["sales_id"],
          sequence_by = "sale_timestamp",
          ignore_null_updates = False,
          apply_as_deletes = None,
          apply_as_truncates = None,
          column_list = None,
          except_column_list = None,
          stored_as_scd_type = 1,
          track_history_column_list = None,
          track_history_except_column_list = None
         )


![image](https://github.com/user-attachments/assets/791a0627-9b2d-461d-b88f-57b08ac7b12b)

![image](https://github.com/user-attachments/assets/0ed9de3c-e8cf-41c7-9b9b-8e38acaeb3b0)

Ahora haremos un ensayo de vista enriquecida, así que, cambiaremos sales_stg_transf por sales_enr_view. En el archivo transform_sales.py.

Código:

        import dlt
        from pyspark.sql.functions import *

        # Transforming Sales Data
        @dlt.view(
            name = "sales_enr_view"   #cambio
        )

        def sales_stg_transf():
             df = spark.readStream.table("sales_stg")
             df = df.withColumn("total_amount", col("quantity") * col("amount"))
             return df
                       

         # Creating Destination Silver
         dlt.create_streaming_table(
           name="sales_enr"
        )

          dlt.create_auto_cdc_flow(
          target = "sales_enr",
          source = "sales_enr_view",      #cambio
          keys = ["sales_id"],
          sequence_by = "sale_timestamp",
          ignore_null_updates = False,
          apply_as_deletes = None,
          apply_as_truncates = None,
          column_list = None,
          except_column_list = None,
          stored_as_scd_type = 1,
          track_history_column_list = None,
          track_history_except_column_list = None
        )
  
Luego ejecutamos en seco 


![image](https://github.com/user-attachments/assets/c942d0c8-d8b6-43ee-ac2a-f92107a0092a)

![image](https://github.com/user-attachments/assets/46ff76e9-2311-4b5b-8607-8934886867e6)

Ahora creamos otro archivo llamado transform_products.py.

![image](https://github.com/user-attachments/assets/2e874d53-d9c0-45ce-98cb-fcb4e2317c34)

![image](https://github.com/user-attachments/assets/7b0b23a6-ab8e-403c-99fa-99e9627dd325)

Ahora pasamos el siguiente código de productos.

Código:

        import dlt
        from pyspark.sql.functions import *
        from pyspark.sql.types import *

        # Transforming Products Data
        @dlt.view(
            name = "products_enr_view"
        )

        def sales_stg_transf():
            df = spark.readStream.table("products_stg")
            df = df.withColumn("price", col("price").cast(IntegerType()))
            return df
                       

        # Creating Destination Silver
        dlt.create_streaming_table(
          name="products_enr"
        )

        dlt.create_auto_cdc_flow(
          target = "products_enr",
          source = "products_enr_view",
          keys = ["product_id"],
          sequence_by = "last_updated",
          ignore_null_updates = False,
          apply_as_deletes = None,
          apply_as_truncates = None,
          column_list = None,
          except_column_list = None,
          stored_as_scd_type = 1,
          track_history_column_list = None,
          track_history_except_column_list = None
        )
  

Y ejecutamos en seco ( Run Dry)


![image](https://github.com/user-attachments/assets/86f572a1-093f-411d-b3c0-7742c23775bf)


Creamos otro archivo llamado transform_customers.

Código:

        import dlt
        from pyspark.sql.functions import *
        from pyspark.sql.types import *

        # Transforming Customers Data
        @dlt.view(
            name = "customers_enr_view"
        )

        def customers_stg_transf():
            df = spark.readStream.table("customers_stg")
            df = df.withColumn("customers_name", upper(col("customers_name")))
            return df
                       

        # Creating Destination Silver
        dlt.create_streaming_table(
        name="customers_enr"
       )

        dlt.create_auto_cdc_flow(
          target = "customers_enr",
          source = "customers_enr_view",
          keys = ["customers_id"],
          sequence_by = "last_updated",
          ignore_null_updates = False,
          apply_as_deletes = None,
          apply_as_truncates = None,
          column_list = None,
          except_column_list = None,
          stored_as_scd_type = 1,
          track_history_column_list = None,
          track_history_except_column_list = None
        )

Ejecutamos en seco.


![image](https://github.com/user-attachments/assets/3e80db23-eb00-461d-b334-328943c277d5)

podemos ver la primera columna nuestra capa de bronce, la segunda columna la vista de enriquecimientos de los datos y la tercera columna la capa de plata.

![image](https://github.com/user-attachments/assets/dba3f93c-ecf0-4eb6-9192-44d2bdb8e9a7)

___________________________________________________________________________________________________________________________________________________________________________________________________________________________

### CAPA GOLD

Crearemos primero la carpeta gold.


![image](https://github.com/user-attachments/assets/92f62a6e-71c3-4395-8ed5-85f45b36c5e5)

Luego, dentro del gold, creamos el archivo dim_products.py.

![image](https://github.com/user-attachments/assets/3a924021-0044-440c-ab4e-1f856f3c7256)

En este proceso haremos una dimensión de cambio lento tipo 2 (SCD – Type 2)

Código:

        import dlt

        # Create Empty Streaming Table
        dlt.create_streaming_table(
            name = "dim_products"
        )

        # AUTO CDC FLOW
        dlt.create_auto_cdc_flow(
            target = "dim_products",
            source = "products_enr_view",
            keys = ["product_id"],
            sequence_by = "last_updated",
            ignore_null_updates = False,
            apply_as_deletes = None,
            apply_as_truncates = None,
            column_list = None,
            except_column_list = None,
            stored_as_scd_type = 2,
            track_history_column_list = None,
            track_history_except_column_list = None
        )


![image](https://github.com/user-attachments/assets/67ad2e91-48c0-4f23-af62-1e2849f64b5c)

![image](https://github.com/user-attachments/assets/d0b89576-f4be-47fd-b3f5-65c3416b2c1a)

Ahora, creamos el archivo dim_customers.py.

![image](https://github.com/user-attachments/assets/abfbb0ac-af41-46e6-99a0-3f41d5c77d1d)


Código:

        import dlt

        # Create Empty Streaming Table
        dlt.create_streaming_table(
            name = "dim_customers"
        )

        # AUTO CDC FLOW
        dlt.create_auto_cdc_flow(
            target = "dim_customers",
            source = "customers_enr_view",
            keys = ["customer_id"],
            sequence_by = "last_updated",
            ignore_null_updates = False,
            apply_as_deletes = None,
            apply_as_truncates = None,
            column_list = None,
            except_column_list = None,
            stored_as_scd_type = 2,
            track_history_column_list = None,
            track_history_except_column_list = None
        )


![image](https://github.com/user-attachments/assets/4c1863ea-28db-4315-9fc3-44362aecabd1)


![image](https://github.com/user-attachments/assets/9c12e913-b455-4a83-aea0-aebce62d8177)

Ahora, creamos una tabla de hechos llamada fact_sales.py.

![image](https://github.com/user-attachments/assets/b26d1d71-3712-44e5-bbe9-b63dc048e61d)


Código:

        import dlt

        # Create Empty Streaming Table
        dlt.create_streaming_table(
            name = "fact_sales"
        )

        # AUTO CDC FLOW
        dlt.create_auto_cdc_flow(
            target = "fact_sales",
            source = "sales_enr_view",
            keys = ["sales_id"],
            sequence_by = "sale_timestamp",
            ignore_null_updates = False,
            apply_as_deletes = None,
            apply_as_truncates = None,
            column_list = None,
            except_column_list = None,
            stored_as_scd_type = 1,
            track_history_column_list = None,
            track_history_except_column_list = None
        )



![image](https://github.com/user-attachments/assets/77f418ce-b3ec-4622-a6c1-105613fb2ee2)

![image](https://github.com/user-attachments/assets/30782203-e098-43b2-abe0-3af6f4234d51)

![image](https://github.com/user-attachments/assets/02b83820-5f40-4c23-957b-ef3df1b68923)

Crearemos el archivo de negocio llamado business_sales.py.

![image](https://github.com/user-attachments/assets/ec08a689-e27b-4023-adaa-40e3a39a95bf)


Código:

        import dlt

        # Create a Materialized View

        @dlt.table(
            name = "business_sales"
        )

        def business_sales():

            df_fact = spark.read.table("fact_sales")
            df_dimCust = spark.read.table("dim_customers")
            df_dimProd = spark.read.table("dim_products")
    
            df_join = df_fact.join(df_dimCust, df_fact.customer_id == df_dimCust.customer_id, "inner").join(df_dimProd, df_fact.product_id == df_dimProd.product_id, "inner")

            df_prun = df_join.select("region", "category", "total_amount")

            return df_prun



![image](https://github.com/user-attachments/assets/9d4ddc96-2d14-4995-a730-d04d8e75fb2c)

![image](https://github.com/user-attachments/assets/450f087f-14ca-4556-8d43-730d13bc1947)


Ahora, haremos la agregación.

Código:

        df_agg = df_prun.groupBy("region", "category").agg(sum("total_amount").alias("total_sales"))


![image](https://github.com/user-attachments/assets/cd3560db-a965-42b7-a017-41b659059ac2)

Finalmente, ejecutamos todo el pipeline (Run Pipeline).

![image](https://github.com/user-attachments/assets/ac92cd08-b332-489b-b9bd-fbb7ccd619f1)

![image](https://github.com/user-attachments/assets/a280dc7a-f04f-4fa5-9448-f51fed66e6af)

Ahora, vamos a SQL Editor en data ware house (DWH) y haremos una carga incremental.

1. hacemos carga incremental en la tabla sales_east.

Código:

        --Incremental table # parte 2
        INSERT INTO sales_east VALUES
        (6, 101, 203, 1, 100.00, '2025-08-02 09:00:00'),
        (7, 106, 206, 2, 250.00, '2025-08-02 09:15:00');


![image](https://github.com/user-attachments/assets/07f04d79-a1c5-4fc4-afa1-491dd7ba5980)

2.	Haremos una carga incremental en la tabla sales_west


Código:

        INSERT INTO sales_west VALUES
        (13, 112, 212, 2, 300.00, '2025-08-02 09:30:00'),
        (14, 107, 208, 1, 130.00, '2025-08-02 09:45:00');



![image](https://github.com/user-attachments/assets/93744eb1-ee19-4f72-b77b-39b2139642a2)

3.	Haremos una carga incremental en la tabla Products.

Código:

        -- Insert 2 (SCD Update)
        -- Price change for product_id 203
        INSERT INTO products VALUES
        (203, 'Monitor', 'Electronics', 90.00, '2025-08-02 08:00:00');

        -- Name change for product_id 208
        INSERT INTO products VALUES
        (208, 'Desk Lamp', 'Furniture', 130.00, '2025-08-02 08:10:00');



![image](https://github.com/user-attachments/assets/9abdfdfd-a399-4346-b412-af622a14aaab)

4.	Hacemos la carga incremental en la tabla customers.

Código:

        Insert 2 (SCD Update)
        -- Region change for customer 103
        INSERT INTO customers VALUES
        (103, 'Charlie', 'Central', '2025-08-02 08:30:00');

        -- Name correction for customer 107
        INSERT INTO customers VALUES
        (107, 'George Smith', 'West', '2025-08-02 08:40:00');



![image](https://github.com/user-attachments/assets/3edca664-ef6a-44f7-93ae-2f055c501468)

![image](https://github.com/user-attachments/assets/318b7b67-045a-4a32-ad3e-724af53b5809)

![image](https://github.com/user-attachments/assets/0e1487d0-9cbd-4d16-bdb3-b51b7be49430)

Ahora, creamos una nueva consulta (query)

![image](https://github.com/user-attachments/assets/19f40a46-a9a1-462a-b012-bc6ebdac80c3)


Código:

        SELECT * FROM dim_products


Previo a ejecutar configuramos recurso y esquema.


![image](https://github.com/user-attachments/assets/c0940f57-7a0b-4bcf-9207-fbf5e49f71d8)

![image](https://github.com/user-attachments/assets/d42f371e-1fa9-42a2-9459-acf8173d920f)

Ahora, veremos las ventas comerciales.

Código:

        SELECT * FROM business_sales

![image](https://github.com/user-attachments/assets/f57f39bc-ab14-4d08-aed5-ab10cd9b9f23)

