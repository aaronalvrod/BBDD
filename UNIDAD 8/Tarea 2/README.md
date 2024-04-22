# Trabajo con la BBDD Jardineria

Se pide realizar los procedimientos y funciones

Realice los siguientes procedimientos y funciones sobre la base de datos jardineria.

- **Función calcular_precio_total_pedido**

    >__Nota__: Dado un código de pedido la función debe calcular la suma total del pedido. Tenga en cuenta que un pedido puede contener varios productos diferentes y varias cantidades de cada producto

    - *Parámetros de entrada:* `codigo_pedido(INT)`
    - *Parámetros de salida: El precio total del pedido (FLOAT)*

            ``` sql
        DELIMITER $$
        DROP FUNCTION IF EXISTS calcular_precio_total_pedido$$
        CREATE FUNCTION calcular_precio_total_pedido(codigo_pedido INT(20) ) RETURNS FLOAT(20)
        BEGIN
            
        ```