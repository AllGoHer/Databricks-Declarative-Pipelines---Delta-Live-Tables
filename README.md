# Databricks-Declarative-Pipelines---Delta-Live-Tables
________________________________________________________________________________________________________________________________________________________________________________________________________________

1.	Creamos un catálogo ejem. dltallgoher y configuramos.

![image](https://github.com/user-attachments/assets/9cc6a0cc-b4c8-417d-8f40-6aa4c2576f9f)

![image](https://github.com/user-attachments/assets/7de2383c-6d5b-4de5-938a-7b6f556ae8e1)

![image](https://github.com/user-attachments/assets/97cd2830-9e4e-417b-9586-0b4b254bab7b)

[image](https://github.com/user-attachments/assets/c39025e7-649f-4074-89a9-ccd1e2650e89)

[image](https://github.com/user-attachments/assets/6c009e94-2c71-46f3-b886-391c99a1c288)

[image](https://github.com/user-attachments/assets/607b6351-7faf-46be-89cc-79d55dbadc76)

* Luego creamos un nuevo espacio de trabajo.
  
[image](https://github.com/user-attachments/assets/2cc8215a-60db-49c3-ad85-caf52c934adb)

[image](https://github.com/user-attachments/assets/3fabd3f8-9243-4f4d-9582-dee1a07aa0a7)

[image](https://github.com/user-attachments/assets/e2081abc-b1ae-4d62-9f1c-6764d652cdb7)

Ahora volvemos a catalogo hacemos click en nuestro catalogo (dtlallgoher) y luego en crear esquema llamado source.

[image](https://github.com/user-attachments/assets/972067bc-6662-4a40-a6fe-70933337c4a3)

[image](https://github.com/user-attachments/assets/e5f909fc-eade-4cdb-a0f4-e4d7603daa3f)

[image](https://github.com/user-attachments/assets/f4e67f62-aaad-43ce-9f47-6aff7ed4ccae)

* Ahora crearemos una tabla

[image](https://github.com/user-attachments/assets/a83987a8-ccbe-45ca-a490-12a9270dc440)

Vamos a sql editor y cambiamos el nombre del New Query Editor por source_orders

[image](https://github.com/user-attachments/assets/ceebe53e-6ed4-4842-ab44-d1ecb84ff448)

[image](https://github.com/user-attachments/assets/dc6a4bc6-5385-4445-b1c5-112ef9645a11)

Primero hacemos click en workspace y seleccionamos dtlallgoher.

[image](https://github.com/user-attachments/assets/de2fbeec-0bf5-4b13-b1b9-8445a628bb58)

Ahora seleccionamos el esquema haciendo click en schema y elegimos source.

[image](https://github.com/user-attachments/assets/985c06cf-934c-40e4-a8ab-a246295d61e5)

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


[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()

[image]()
