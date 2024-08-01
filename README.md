# Bird-strike-analysis
 ● Yearly Analysis & Bird Strikes in the US
 Yealy Bird strike =
 SUMX(
 SUMMARIZE(Birdstrike,Birdstrike[FlightDate].[Year],"Strikes",[total strikes]),[total strikes]
 )
 ● Top 10 US Airlines in terms of having encountered bird strikes
 top10airline = 
 SUMX(
 SUMMARIZE(Birdstrike,Birdstrike[Aircraft: Airline/Operator],"Strikes",[total strikes]),[total strikes]
 )
 
 ● Airports with most incidents of bird strikes – Top 50
 top10airline = 
 SUMX(
 SUMMARIZE(Birdstrike,Birdstrike[Aircraft: Airline/Operator],"Strikes",[total strikes]),[total strikes]
 )
 
 ● Yearly Cost Incurred due to Bird Strikes:
YEARLY COST =
SUMX(
VALUES(Birdstrike[FlightDate].[Year]), CALCULATE(
SUM(Birdstrike[Cost: Total $])
))
 
 ● When do most bird strikes occur?
 which month has most strikes =
 CALCULATE(
 COUNT(Birdstrike[Record ID]),month(Birdstrike[FlightDate])
 )
 
 ● Altitude of aeroplanes at the time of strike
Atitude = 
SUMX(
SUMMARIZE(Birdstrike,Birdstrike[Altitude in feet],"Strikes",[total strikes]),CALCULATE(COUNT(Birdstrike[Record ID])
))
 
 ● Phase of flight at the time of the strike.
Phase of flight =
SUMX(
SUMMARIZE(Birdstrike,Birdstrike[When: Phase of flight],"Strikes",[total strikes]),[total strikes])
 
 ● Average Altitude of the aeroplanes in different phases at the time of strike
avg altitude = 
SUMX(
SUMMARIZE(Birdstrike,Birdstrike[When: Phase of flight],"Avg Strikes",
AVERAGE(Birdstrike[Feet above ground])),
CALCULATE(AVERAGE(Birdstrike[Feet above ground]))
)
 
 ● Effect of Bird Strikes & Impact on Flight
Impact on flight = 
SUMX(
SUMMARIZE(Birdstrike,Birdstrike[Effect: Impact to flight],"Strikes",[total strikes]),[total strikes])

 
 ● Were Pilots Informed? & Prior Warning and Effect of Strike Relation
Prior warning =
SUMX(
SUMMARIZE(Birdstrike,Birdstrike[Pilot warned of birds or wildlife?],"Strikes",[total strikes]),[total strikes]
)
 
