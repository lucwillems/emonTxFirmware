# Discrete Sampling full

this sketch add new extra data to emonhub/cms :

```
   Power ct 1..4
   Vrms
   Temperature 1..6
   PulseCount
   Frequency
   Power factor
 ```
 
the reason for adding Frequency and Power Factor is to use this information
for evaluation of power consumption (PF) and the overall load of the power grid

https://en.wikipedia.org/wiki/Utility_frequency

in high power load, frequence should drop below 49.5 Hz (on 50 Hz grid) , indicating
possible higher load. in europe , freq below 49..48 Hz will cause blackout scenarios.
 
As i live in belgium , currently (16/01/2016) we have all our nuclear power plants
running and exporting power so freq is stable around 50.0 Hz
 
## installation

 - ACAC adopter is required ! can't measure frequency without it
 - Update emonlib (see https://github.com/lucwillems/EmonLib ) is required
 - This sketch
 - Update your emonhub configuration as shown below

## emonhub configuration:

this sketch has but the emonv3 on address 11 and has following configuration for emonhub:

```
[[11]]
    nodename = Tx_Test
    firmware = V2_3_emonTxV3_4_DiscreteSampling_full
    hardware = emonTx_(NodeID_DIP_Switch1:OFF)
    [[[rx]]]
       names =  power1, power2, power3, power4, Vrms, temp1, temp2, temp3, temp4, temp5, temp6, pulse, freq, pf1, pf2, pf3, pf4
       datacodes = h,h,h,h,h,h,h,h,h,h,h,L,h,f,f,f,f
       scales =    1,1,1,1,0.01,0.1,0.1, 0.1,0.1,0.1,0.1,.01,.01,1,1,1,1
       units =     W,W,W,W,V,C,C,C,C,C,C,p,Hz,%,%,%,%
```
## Live example of power usage/Factor, Main voltage and freq of a location in belgium

 http://emoncms.org/dashboard/view?id=30272
