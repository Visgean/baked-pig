# Apache pig with example files:

Image with examples from https://www.tutorialspoint.com/apache_pig/apache_pig_join_operator.htm


Based on [hakanserce/docker-apache-pig](https://hub.docker.com/r/hakanserce/docker-apache-pig/), adds examples

# Pull the image
```
docker pull visgean/baked-pig
```

# Start a container
In order to use the Docker image use:

```
docker run -i -t visgean/baked-pig /etc/bootstrap.sh -bash
```


## Start a container

In order to use the Docker image use:

```
	docker run -i -t visgean/baked-pig /etc/bootstrap.sh -bash
```

Start pig in local mode:

```
pig -x local
```


# Examples:

```
customers = LOAD '/examples/customers.txt' USING PigStorage(',')
   as (id:int, name:chararray, age:int, address:chararray, salary:int);
  
orders = LOAD '/examples/orders.txt' USING PigStorage(',')
   as (oid:int, date:chararray, customer_id:int, amount:int);


coustomer_orders = JOIN customers BY id, orders BY customer_id;
Dump coustomer_orders;

```