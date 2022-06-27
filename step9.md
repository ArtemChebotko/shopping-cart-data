<div class="top">

# Design query Q5
### [◂](command:katapod.loadPage?step8){.steps} Step 9 of 10 [▸](command:katapod.loadPage?step10){.steps}
</div>

Find all items and their subtotal for a cart with id `19925cc1-4f8b-4a44-b893-2a49a8434fc8`; order items by timestamp (desc):

<details>
  <summary>Solution</summary>

```
SELECT timestamp, item_id, item_price, 
       quantity, cart_subtotal 
FROM items_by_cart
WHERE cart_id = 19925cc1-4f8b-4a44-b893-2a49a8434fc8; 
```

</details>

[continue](command:katapod.loadPage?step10){.orange_bar}
