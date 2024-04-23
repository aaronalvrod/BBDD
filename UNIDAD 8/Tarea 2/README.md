# Trabajo con la BBDD Jardineria

Se pide realizar los procedimientos y funciones

Realice los siguientes procedimientos y funciones sobre la base de datos jardineria.

- **Función calcular_precio_total_pedido**

    >__Nota__: Dado un código de pedido la función debe calcular la suma total del pedido. Tenga en cuenta que un pedido puede contener varios productos diferentes y varias cantidades de cada producto

    - *Parámetros de entrada:* `codigo_pedido(INT)`
    - *Parámetros de salida: El precio total del pedido (FLOAT)*

            ``` sql
        DELIMITER //

        CREATE FUNCTION calcular_precio_total_pedido(codigo_pedido INT)
        RETURNS FLOAT
        BEGIN
            DECLARE total_pedido FLOAT;
            
            SELECT SUM(precio * cantidad)
            INTO total_pedido
            FROM productos_pedido
            WHERE id_pedido = codigo_pedido;
            
            RETURN total_pedido;
        END //

        DELIMITER ;
        ```


        ``` sql
        DELIMITER //

        CREATE FUNCTION calcular_suma_pedidos_cliente(codigo_cliente INT)
        RETURNS FLOAT
        BEGIN
            DECLARE total_pedidos_cliente FLOAT;
            
            SELECT SUM(calcular_precio_total_pedido(id_pedido))
            INTO total_pedidos_cliente
            FROM pedidos
            WHERE codigo_cliente = codigo_cliente;
            
            RETURN total_pedidos_cliente;
        END //

        DELIMITER ;
        ```

        ``` sql
        DELIMITER //

        CREATE FUNCTION calcular_suma_pagos_cliente(codigo_cliente INT)
        RETURNS FLOAT
        BEGIN
            DECLARE total_pagos_cliente FLOAT;
            
            SELECT SUM(monto)
            INTO total_pagos_cliente
            FROM pagos
            WHERE codigo_cliente = codigo_cliente;
            
            RETURN total_pagos_cliente;
        END //

        DELIMITER ;
        ```

        ``` sql
        DELIMITER //

        CREATE PROCEDURE calcular_pagos_pendientes()
        BEGIN
            DECLARE cliente_id INT;
            DECLARE total_pedidos FLOAT;
            DECLARE total_pagos FLOAT;
            
            DECLARE done INT DEFAULT FALSE;
            DECLARE cur_clientes CURSOR FOR SELECT DISTINCT codigo_cliente FROM pedidos;
            DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
            
            OPEN cur_clientes;
            read_loop: LOOP
                FETCH cur_clientes INTO cliente_id;
                IF done THEN
                    LEAVE read_loop;
                END IF;
                
                SET total_pedidos = calcular_suma_pedidos_cliente(cliente_id);
                SET total_pagos = calcular_suma_pagos_cliente(cliente_id);
                
                IF total_pedidos > total_pagos THEN
                    SELECT CONCAT('Cliente ', cliente_id, ' tiene pagos pendientes de ', total_pedidos - total_pagos) AS Mensaje;
                END IF;
            END LOOP;
            
            CLOSE cur_clientes;
        END //

        DELIMITER ;
        ``` 