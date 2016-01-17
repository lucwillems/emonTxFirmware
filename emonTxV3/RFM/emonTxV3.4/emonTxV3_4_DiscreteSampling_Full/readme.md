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
 

emonhub configuration:

this sketch has but the emonv3 on address 11 and has following configuration for emonhub:

[[11]]
    nodename = Tx_Test
    firmware = V2_3_emonTxV3_4_DiscreteSampling_full
    hardware = emonTx_(NodeID_DIP_Switch1:OFF)
    [[[rx]]]
       names =  power1, power2, power3, power4, Vrms, temp1, temp2, temp3, temp4, temp5, temp6, pulse, freq, pf1, pf2, pf3, pf4
       datacodes = h,h,h,h,h,h,h,h,h,h,h,L,h,f,f,f,f
       scales =    1,1,1,1,0.01,0.1,0.1, 0.1,0.1,0.1,0.1,.01,.01,1,1,1,1
       units =     W,W,W,W,V,C,C,C,C,C,C,p,Hz,%,%,%,%
