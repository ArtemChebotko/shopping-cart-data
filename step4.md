<div class="top">

# Design query Q1
### [◂](command:katapod.loadPage?step3){.steps} Step 4 of 10 [▸](command:katapod.loadPage?step5){.steps}
</div>

Find id and name of an active shopping cart that belongs to user `jen`:
 
<details>
  <summary>Solution 1 (preferred)</summary>

```
-- Retrieve all carts for jen
-- and scan the result set
-- within an application
-- to find an active cart.
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen';
```

</details>

<br/>

<details>
  <summary>Solution 2</summary>

```
-- Retrieve all carts for jen
-- and scan the result set
-- within Cassandra
-- to find an active cart.
-- Note that this is a rare case of
-- scanning within a small partition
-- when ALLOW FILTERING 
-- might be acceptable. 
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen'
  AND cart_is_active = true 
ALLOW FILTERING;
```

</details>

[continue](command:katapod.loadPage?step5){.orange_bar}