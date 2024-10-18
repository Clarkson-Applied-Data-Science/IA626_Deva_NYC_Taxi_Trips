# IA626_Deva_NYC_Taxi_Trips

# 1.	What datetime range does your data cover?  How many rows are there total?

- Min_Datetime: 2013-11-01 00:00:00
- Max_Datetime: 2013-12-01 01:47:54
- The total number of rows in the data: 14388451

# 2.	What are the field names?  Give descriptions for each field.

Field                    | Description
------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------
medallion                | This field refers to permit number indicating the vehicle can be operated as a taxi.
hack_license             | This field refers to license number that allows a person to operate a taxi.
vendor_id                | This field indicates the vendor/company code for the taxi vehicle.
rate_code                | This field refers to different types of rate categories for the taxi.
store_and_fwd_flag       | This field indicates whether the trip record was stored in the vehicle memory before forwarding to the server.
pickup_datetime          | This field indicates the date and time of passenger pick up.
dropoff_datetime         | This field indicates the date and time of passenger drop off.
passenger_count          | This field indicates the count/number of passengers.
trip_time_in_secs        | This field indicates the duration of the trip in seconds.
trip_distance            | This field indicates the distance covered for the trip.
pickup_longitude         | This field indicates the longitude coordinates for the pickup location of the trip.
pickup_latitude          | This field indicates the latitude coordinates for the pickup location of the trip.
dropoff_longitude        | This field indicates the longitude coordinates for the drop off location of the trip.
dropoff_latitude         | This field indicates the latitude coordinates for the drop off location of the trip.

# 3.	Give some sample data for each field.
| medallion                          | hack_license                       | vendor_id   | rate_code   | store_and_fwd_flag   | pickup_datetime       | dropoff_datetime      | passenger_count   | trip_time_in_secs   | trip_distance   | pickup_longitude   | pickup_latitude   | dropoff_longitude   | dropoff_latitude   |
|------------------------------------|------------------------------------|-------------|-------------|----------------------|-----------------------|-----------------------|-------------------|---------------------|-----------------|--------------------|-------------------|---------------------|--------------------|
| E9A54865CAF737ED003957478C9D8FA1   | 912A2B86F30CDFE246586972A892367E   | CMT         | 1           | N                    | 2013-11-25 15:53:33   | 2013-11-25 16:00:51   | 1                 | 437                 | 0.60             | -73.978104         | 40.752968         | -73.985756          | 40.762684          |
| 43D85E4D101135DDFC1BC16DF53665FE   | B2981CEA18FB7E9D8E676EF228257AD1   | CMT         | 1           | N                    | 2013-11-25 15:24:41   | 2013-11-25 15:30:18   | 1                 | 336                 | 0.50             | -73.982315         | 40.764828         | -73.982132          | 40.758888          |
| 70166F37A5CC66D9A35366764ACC40DC   | 1BAF0067863EA446E21314F88A600B4D   | CMT         | 1           | N                    | 2013-11-25 09:43:42   | 2013-11-25 10:02:57   | 1                 | 1154                | 3.30            | -73.98201          | 40.762508         | -74.006851          | 40.719582          |

# 4.	What MySQL data types / len would you need to store each of the fields?
## a.	int(xx), varchar(xx),date,datetime,bool, decimal(m,d)
Field                    | Datatypes(len)
------------------------- | -----------------
medallion                | CHAR(32)
hack_license             | CHAR(32)
vendor_id                | CHAR(3)
rate_code                | INT
store_and_fwd_flag       | BOOLEAN
pickup_datetime          | DATETIME
dropoff_datetime         | DATETIME
passenger_count          | INT
trip_time_in_secs        | INT
trip_distance            | FLOAT
pickup_longitude         | DECIMAL(9, 6)
pickup_latitude          | DECIMAL(9, 6)
dropoff_longitude        | DECIMAL(9, 6)
dropoff_latitude         | DECIMAL(9, 6)

# 5.	What is the geographic range of your data (min/max - X/Y)?
## a.	Plot this (approximately on a map)

Coordinate | Min        | Max        
-----------|------------|------------
Longitude  | -74.031761 | -73.924896 
Latitude   | 40.682972  | 40.818737  

<img width="866" alt="{0B76B053-766A-4E30-A7D8-F834DDAD5926}" src="https://github.com/user-attachments/assets/03e8f195-5c5a-485a-86ed-2c13423a3bad">


# 6.	What is the average overall computed trip distance? (You should use Haversine Distance)
## a.	Draw a histogram of the trip distances binned anyway you see fit.

Attribute             | Value      
----------------------|------------
Average Trip Distance | 10.33 miles 

![image](https://github.com/user-attachments/assets/c25b78de-28fe-4437-ab33-ab4d133dd9b7)

# 7.	What are the distinct values for each field? (If applicable)
Field                   | Distinct Values                                                                                     
------------------------|---------------------------------------------------------------------------------------------------- 
rate_code               | ['2', '8', '0', '7', '210', '6', '10', '5', '4', '9', '3', '1']                                  
vendor_id               | ['CMT', 'VTS']                                                                                    
store_and_fwd_flag      | ['', 'Y', 'N']                                                                                    
passenger_count         | ['2', '8', '208', '0', '7', '6', '5', '4', '9', '3', '1']                                       

# 8.	For other numeric types besides lat and lon, what are the min and max values?

Field                | Min | Max    
---------------------|-----|--------
Trip Time (seconds)  | 0   | 10800  
Trip Distance        | 0.0 | 100.0  
Passenger Count      | 0   | 208    
Rate Code            | 0   | 210    

# 9.	Create a chart which shows the average number of passengers each hour of the day. (X axis should have 24 hours)

![image](https://github.com/user-attachments/assets/d671fd5c-c005-4f33-826f-d5a0a50d843c)

# 10.	Create a new CSV file which has only one out of every thousand rows.
New CSV file with every 1000th row from the existing file has been created.

# 11.	Repeat step 9 with the reduced dataset and compare the two charts.

![image](https://github.com/user-attachments/assets/ba6aeaba-59f7-4be0-835e-7bd352e5f613)

By comparing the sample/reduced dataset chart with the original one, we can observe that:
Both datasets indicate higher passenger numbers in the early AM hours, but the reduced dataset highlights this more sharply.
Average Passengers for larger dataset are fairly stable throughout the day, with a slight dip around 5am - 10am, whereas the peak for the reduced dataset is around 1am - 3am with a sudden dip after 3am.
