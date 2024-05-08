
# Golden metrics (Traffic, Latency, Errors, Saturation)

## Latency example
Example for Latency 
* split views successful / failed 

![](imgs/Latency.jpg)

## Errors example

Errors thrown by the APIM gateway
* ((ResponseCode > 499 or ResponseCode == 0) and BackendResponseCode <> ResponseCode) 
* (BackendResponseCode == 200 and ResponseCode == 200 and IsRequestSuccess == false)

[] are failed OPTIONS calls with ResponseCode == 0

![](imgs/APIM_5xx.jpg)

Drill down into ClientConnectionFailures

![](imgs/ClientConnectionFailure.jpg)