# Electric-Vehicle-analysis-Using-MYSQL
I have performed various queries on electric vehicle dataset which are below:

#1 Retrieve all vehicles from a specific city which is seattle
SELECT * FROM ev.electric_vehicle_population_data 
WHERE City = 'Seattle';

#2 Find the total number of electric vehicles in the dataset
SELECT COUNT(*) AS TotalElectricVehicles
FROM ev.electric_vehicle_population_data;

#3 Retrieve vehicles from King County with an electric range greater than 200 miles and a base MSRP less than $50,000
SELECT * FROM electric_vehicle_population_data 
WHERE County = 'King' AND 
`Electric Range` > 200 AND 
`Base MSRP` < 50000;

#4 Calculate the average electric range for each electric vehicle type
SELECT `Electric Vehicle Type`, AVG(`Electric Range`) AS AvgRange 
FROM electric_vehicle_population_data 
GROUP BY `Electric Vehicle Type`;

#5 Identify the cities where the total number of electric vehicles is higher than 10
SELECT City, COUNT(*) AS TotalVehicles 
FROM electric_vehicle_population_data 
GROUP BY City 
HAVING TotalVehicles > 10;

#6 Find the average electric range and base MSRP for each make of electric vehicles
SELECT Make, AVG(`Electric Range`) AS AvgRange, 
AVG(`Base MSRP`) AS AvgMSRP
FROM electric_vehicle_population_data
GROUP BY Make;

#7 Find the total count of electric vehicles for each model year:
SELECT `Model Year`, COUNT(*) AS VehicleCount
FROM electric_vehicle_population_data
GROUP BY `Model Year`;

#8 Find the average electric range for each combination of make and model
SELECT Make, Model, AVG(`Electric Range`) AS AvgRange
FROM electric_vehicle_population_data
GROUP BY Make, Model;
