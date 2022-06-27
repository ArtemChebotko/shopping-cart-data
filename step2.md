<div class="top">

# Create tables
### [◂](command:katapod.loadPage?step1){.steps} Step 2 of 10 [▸](command:katapod.loadPage?step3){.steps}
</div>

Create table `carts_by_user`:
```
CREATE TABLE carts_by_user (
  user_id TEXT,
  cart_name TEXT,
  cart_id UUID,
  cart_is_active BOOLEAN,
  user_email TEXT STATIC,
  PRIMARY KEY ((user_id),cart_name,cart_id)
);
```

Create table `items_by_id`:
```
CREATE TABLE items_by_id (
  id TEXT,
  name TEXT,
  description TEXT,
  price DECIMAL,
  PRIMARY KEY ((id))
);
```

Create materialized view `items_by_name`:
```
CREATE MATERIALIZED VIEW items_by_name 
  AS 
    SELECT * FROM items_by_id
    WHERE name IS NOT NULL 
      AND id IS NOT NULL
  PRIMARY KEY ((name), id);
```


Create table `items_by_cart`:
```
CREATE TABLE items_by_cart (
  cart_id UUID,
  timestamp TIMESTAMP,
  item_id TEXT,
  item_name TEXT,
  item_description TEXT,
  item_price DECIMAL,
  quantity INT,
  cart_subtotal DECIMAL STATIC,
  PRIMARY KEY ((cart_id),timestamp,item_id)
) WITH CLUSTERING ORDER BY (timestamp DESC, item_id ASC);
```

[continue](command:katapod.loadPage?step3){.orange_bar}