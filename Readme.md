
## Start a container

In order to use the Docker image use:

```
	docker run -i -t hakanserce/apache-pig /etc/bootstrap.sh -bash
```

locally:


	docker run -i -t e98bb7850a95 /etc/bootstrap.sh -bash



pig -x local

# Examples:

```
customers = LOAD '/examples/customers.txt' USING PigStorage(',')
   as (id:int, name:chararray, age:int, address:chararray, salary:int);
  
orders = LOAD '/examples/orders.txt' USING PigStorage(',')
   as (oid:int, date:chararray, customer_id:int, amount:int);


coustomer_orders = JOIN customers BY id, orders BY customer_id;
Dump coustomer_orders;

```