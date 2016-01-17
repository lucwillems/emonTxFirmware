Discrete Sampling full

this sketch add new extra data to emonhub/cms :
 - Power ct 1..4
 - Vrms
 - Temperature 1..6
 - pulseCount
 - Frequency
 - Power factor
 
 
 the reason for adding Frequency and Power Factor is to use this information
 for evaluation of power consumption (PF) and the overall load of the power grid
 
 in high power load, frequence should drop below 49 Hz (on 50 Hz grid) , indicating
 possible blackout scenarios.
 
 As i live in belgium , currently (16/01/2016) we have all our nuclear power plants
 running and exporting power so freq is stable around 50.0 Hz
  