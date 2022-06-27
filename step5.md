<div class="top">

# Design query Q4
### [◂](command:katapod.loadPage?step4){.steps} Step 5 of 10 [▸](command:katapod.loadPage?step6){.steps}
</div>

Find ids and names of all shopping carts that belong to user `jen`; order by cart name (asc):
 
<details>
  <summary>Solution</summary>

```
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen';
```

</details>

[continue](command:katapod.loadPage?step6){.orange_bar}