<div class="top">

# Create a keyspace
### [◂](command:katapod.loadPage?intro){.steps} Step 1 of 10 [▸](command:katapod.loadPage?step2){.steps}
</div>

Start the CQL shell:
```
cqlsh
```

Create the `shopping_cart_data` keyspace:
```
CREATE KEYSPACE shopping_cart_data
WITH replication = {
  'class': 'NetworkTopologyStrategy', 
  'DC-Houston': 1 };
```

Set the current working keyspace:
```
USE shopping_cart_data;
```

[continue](command:katapod.loadPage?step2){.orange_bar}