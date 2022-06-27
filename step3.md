<div class="top">

# Populate tables
### [◂](command:katapod.loadPage?step2){.steps} Step 3 of 10 [▸](command:katapod.loadPage?step4){.steps}
</div>

Execute the CQL script to insert sample data:
```
SOURCE 'assets/shopping_cart_data.cql'
```

Retrieve all rows from table `carts_by_user`:
```
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user;        
```

Retrieve all rows from table `items_by_id`:
```
SELECT * FROM items_by_id;
```

Retrieve all rows from materialized view `items_by_name`:
```
SELECT * FROM items_by_name;                    
```

Retrieve all rows from table `items_by_cart`:
```
SELECT cart_id, timestamp, item_id 
FROM items_by_cart; 

SELECT cart_id, item_id, item_price, 
       quantity, cart_subtotal 
FROM items_by_cart; 
```

[continue](command:katapod.loadPage?step4){.orange_bar}