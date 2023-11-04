

# Aggregating Functions
2.1.1
```sql
WITH PassengerFlights AS (
    SELECT
        split_part(passenger_name, ' ', 1) AS first_name,
        split_part(passenger_name, ' ', 2) AS last_name,
        date(f.scheduled_departure) AS date,
        f.scheduled_departure::timestamp::time AS time,
        tf.fare_conditions AS booking_class,
        tf.amount,
        SUM(tf.amount) OVER (PARTITION BY passenger_name ORDER BY f.scheduled_departure) AS cumulative_amount,
        COUNT(*) OVER (PARTITION BY passenger_name) AS total_flights
    FROM
        tickets t
    JOIN
        ticket_flights tf ON tf.ticket_no = t.ticket_no
    JOIN
        flights f ON f.flight_id = tf.flight_id
)
SELECT
    first_name,
    last_name,
    date,
    time,
    booking_class,
    amount,
    cumulative_amount AS current_flight_amount,
    total_flights AS total_sum_of_flights
FROM
    PassengerFlights
```

![[Pasted image 20231104194734.png]]


2.1.2
Added to previous code
```sql
WHERE first_name = 'ADELINA';
```

![[Pasted image 20231104195055.png]]


# Ranking Functions
2.1.2
```sql
WITH FirstFlights AS (
    SELECT
        a.model AS aircraft_model_name,
        MIN(f.scheduled_departure) AS first_flight_date_time
    FROM
        flights f
    JOIN
        aircrafts a ON f.aircraft_code = a.aircraft_code
    GROUP BY
        a.model
)
SELECT
    aircraft_model_name,
    first_flight_date_time
FROM
    FirstFlights;

```
![[Pasted image 20231104195255.png]]

2.2.2
```sql
WITH LastFlights AS (
    SELECT
        a.model AS aircraft_model_name,
        MAX(f.scheduled_departure) AS last_flight_date_time
    FROM
        flights f
    JOIN
        aircrafts a ON f.aircraft_code = a.aircraft_code
    GROUP BY
        a.model
)
SELECT
    aircraft_model_name,
    last_flight_date_time
FROM
    LastFlights;

```
![[Pasted image 20231104195320.png]]

2.2.3
```sql
WITH AircraftFlightCounts AS (
    SELECT
        a.model AS aircraft_model_name,
        COUNT(*) AS total_flights
    FROM
        flights f
    JOIN
        aircrafts a ON f.aircraft_code = a.aircraft_code
    GROUP BY
        a.model
)
SELECT
    aircraft_model_name,
    total_flights,
    RANK() OVER (ORDER BY total_flights DESC) AS ranking
FROM
    AircraftFlightCounts;

```

![[Pasted image 20231104195346.png]]


# 2.2.1 Joins Edition

1.
```sql
select flight_id, departure_airport, arrival_airport, ad.*, ad2.* from flights f

join airports_data ad on ad.airport_code = f.departure_airport

join airports_data ad2 on ad2.airport_code = f.arrival_airport
```
![[Pasted image 20231104200142.png]]

2.
```sql
select ticket_no, f.*, ad.* from ticket_flights tf 
join flights f on f.flight_id = tf.flight_id 
join aircrafts_data ad on ad.aircraft_code = f.aircraft_code 
```
![[Pasted image 20231104200426.png]]

3.
```sql
select airport_code, count(*), avg(scheduled_departure - actual_departure) from airports a

join flights f on f.departure_airport = a.airport_code

group by airport_code;
```
![[Pasted image 20231104200858.png|600x300]]

4.
```sql
SELECT
    f.flight_id,
    COUNT(tf.ticket_no) AS tickets_sold,
    MAX(a.model) AS aircraft_model,
    MAX(a.aircraft_code) AS aircraft_code
FROM
    flights f
JOIN
    ticket_flights tf ON tf.flight_id = f.flight_id
JOIN
    aircrafts a ON a.aircraft_code = f.aircraft_code
GROUP BY
    f.flight_id;
```
![[Pasted image 20231104202444.png]]


5.
```sql
SELECT
    f.flight_id,
    MAX(tf.amount) AS price,
    MAX(a.model) AS aircraft_model
FROM
    flights f
JOIN
    ticket_flights tf ON tf.flight_id = f.flight_id
JOIN
    aircrafts a ON a.aircraft_code = f.aircraft_code
GROUP BY
    f.flight_id;
```

![[Pasted image 20231104202646.png]]

6.
```sql
select f.flight_id, count(*) as passenger_num from flights f
join ticket_flights tf on tf.flight_id = f.flight_id 
group by f.flight_id 
```
![[Pasted image 20231104203016.png]]

7.
```sql
select f.flight_id, tf.fare_conditions, count(*) as tickets_sold from flights f 
join ticket_flights tf on tf.flight_id = f.flight_id 
group by f.flight_id, tf.fare_conditions 
```
![[Pasted image 20231104203311.png]]


8.
```sql
SELECT
    f.flight_id,
    f.flight_no,
    SUM(CASE WHEN tf.fare_conditions = 'Business' THEN 1 ELSE 0 END) AS business_class_seats,
    SUM(CASE WHEN tf.fare_conditions = 'Economy' THEN 1 ELSE 0 END) AS economy_class_seats
FROM
    flights f
JOIN
    ticket_flights tf ON f.flight_id = tf.flight_id
GROUP BY
    f.flight_id, f.flight_no;
```
![[Pasted image 20231104203821.png]]

9.
```sql
SELECT
    f.flight_id,
	f.flight_no,
    SUM(CASE WHEN tf.fare_conditions = 'Business' THEN 1 ELSE 0 END) AS business_class_seats,
    SUM(CASE WHEN tf.fare_conditions = 'Economy' THEN 1 ELSE 0 END) AS economy_class_seats,
    count(ticket_no) as number_of_sold_tickets
FROM
    flights f
JOIN
    ticket_flights tf ON f.flight_id = tf.flight_id
GROUP BY
    f.flight_id, f.flight_no;
```
![[Pasted image 20231104204017.png]]

10.
```sql
SELECT
    f.flight_id,
    f.flight_no ,
    AVG(CASE WHEN tf.fare_conditions = 'Business' THEN tf.amount ELSE NULL END) AS avg_business_class_cost,
    AVG(CASE WHEN tf.fare_conditions = 'Economy' THEN tf.amount ELSE NULL END) AS avg_economy_class_cost
FROM
    flights f
JOIN
    ticket_flights tf ON f.flight_id = tf.flight_id
GROUP BY
    f.flight_id, f.flight_no ;
```
![[Pasted image 20231104204155.png]]

# 2.2.2 Subqueries
1.
```sql
WITH AirportFlightCounts AS (
    SELECT
        a.airport_code,
        COUNT(f.flight_id) AS numbers_of_flights
    FROM
        airports a
    JOIN
        flights f ON f.departure_airport = a.airport_code
    GROUP BY
        a.airport_code
)
SELECT
    a.airport_code
FROM
    airports a
JOIN
    AirportFlightCounts afc ON a.airport_code = afc.airport_code
WHERE
    afc.numbers_of_flights > (SELECT ROUND(AVG(numbers_of_flights)) FROM AirportFlightCounts)
GROUP BY
    a.airport_code;

```
![[Pasted image 20231104205231.png]]

2.
```sql
select
    f.flight_id
from
    flights f
join
    ticket_flights tf on f.flight_id = tf.flight_id
group by
    f.flight_id
having
    sum(tf.amount) > (select avg(amount) from ticket_flights);
```
![[Pasted image 20231104205556.png]]

3.
```sql
select
    f.departure_airport,
    floor(avg(extract(epoch from (f.actual_arrival - f.actual_departure))) ) as average_flight_duration
from
    flights f
group by
    f.departure_airport;

```
![[Pasted image 20231104210322.png]]

4.
```sql
SELECT
    arrival_airport,
    COUNT(DISTINCT a.model) AS number_of_different_models
FROM
    flights f
JOIN
    aircrafts a ON f.aircraft_code = a.aircraft_code
GROUP BY
    arrival_airport
ORDER BY
    number_of_different_models DESC
LIMIT 2;
```
![[Pasted image 20231104210537.png]]


5.
```sql
SELECT
    f1.departure_airport
FROM
    flights f1
JOIN
    airports a ON f1.departure_airport = a.airport_code
LEFT JOIN
    (
        SELECT DISTINCT arrival_airport
        FROM flights
    ) f2 ON f1.departure_airport = f2.arrival_airport
WHERE
    f2.arrival_airport IS NULL
GROUP BY
    f1.departure_airport
HAVING
    COUNT(DISTINCT a.airport_code) = COUNT(f2.arrival_airport) + 1;

```
![[Pasted image 20231104211647.png]]