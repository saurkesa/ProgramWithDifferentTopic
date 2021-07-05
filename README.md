# ProgramWithDifferentTopic

#Refer Aditya verma playlist in you tube

                                                      Topic 1) Recursion:-
HIB( Hypothesis Induction base condtion)
base condition: smallest valid input
hypothesis:---method
Induction: --logic

NOTE: first create hypotheis ( means function) then base condtion then induction( smaller input)

TRICK:- always store one element into variable then do induction( see aditya video it will clear more)

sort stack using recursion:
https://www.youtube.com/watch?v=lDThYwMDNTU&t=694s

========================================================================
2) powerset ---ab------{a,b,ab} ----all subset of a set is called powerset

   subset- order not matter like it is bag ----------example abc----ac ,ca (both are possbile)

   subsequences----order matter and it is like chain ----------example abc---- ac possible but ca not possible
   
   substring :---string should be in continous
   
                                  
                                  Topic 2: Binary Search
                                  
  Identification: if array is sorted then always think to use binary search
     
Binary search works on sorted arrays. Binary search begins by comparing an element in the middle of the array with the target value. If the target value matches the element, its position in the array is returned. If the target value is less than the element, the search continues in the lower half of the array.

Peak element: will be greater of both it neighbour element
note : for first and last element only one neighbour is there so they will check with that if it is greater then that will be peak element

Bitonic Array: An array is said to be bitonic if the elements in the array are first strictly increasing then strictly decreasing

Problem: search element in bitonic array
first find peak element then call two binary search tree and search element.
bst(0,peak-1,arr,element) bst(peak, arr.length-1,arr,element)

                                                   Topic 3) Stack
                                                   
 Identification) whwre we can use stack : if second loop is depend on i( first loop) then think to use stack
 
 for(int i=0; i< n;i++)
 {
 for(int j=0; j<i; j++)
 {
 
  here j is depenedent on i   ---------    0----------i---------------n
   j---->  0---i j++
   
   j----> i----0 j-- 
   
   j----> i----n j++
   
   j----> n----i j--
   
   }
   
  a) Stock span problem : consecutive smaller or equivalen before it
   
 b)  Maximum area histogram (MAH)  
 
    width = NSR(index) - NSL(index)-1
   
   Area[i] = arr[i] * width[i];
   
   from area find maximum
  
                                                  Topic 4- Heap
    
 Identification:-
 1)k
 
 2)smallest/largest
 
 NOTE: k+smallest ---max heap will make and k+largest ---min heap will create
 
 
This library module defines the highlevel logic and abstractions of the Cloud IBES profiler.

Two main abstractions are defined here: Data Reader and Device Package.

Data reader abstracts collection data reading. Initially we support data from cloud collector and DNAC, but additional file format can be supported in the future.
Device package abstracts out device data profiling. Initially we support device data from cloud collector and DNAC, but additional device data format can be supported in the future.

One or more reader and device package modules can be `plugged` in by registering its `selector`. Selector is the interface that would return a reader for a given collection data format or a device package for a given device data.

## Profiler
This library module defines the main abstractions of the 'profiler'. Profiler is a function that takes collection metadata as its input and returns an array of profiled data.

![Profiler](docs/profiler.png)

1. Profiler gets the Input Reader, DP (Device Package), Post Processor based on the DataSource in Collection Meta-Data
2. Profiler will invoke the Input Reader to read the inventory file
3. Input Reader returns Slice of Raw Device data which will be input for Profiling
4. Simple Profiler/Concurrent Profiler will invoke DP for each Raw DeviceData, DP profiles the Raw data and returns Profiled device data
5. Profiler will perform Deduplication, Post Processing based on the DataSource
6. Inventory Common IBES Data Model will be added to cache

## Build

```
make all
```

## Distribution

```
make dist
```

## Usage
Profiler Library can be used as binary executable as well as it can be imported as a library. Usage of both has been illustrated with an example below.

### CLI
#### Profiler
Execute the binary by passing the required arguments like -InputFilePath, -WorkerThreadCount, -DataSource, -DataFormat, -OutputFilePath
* -InputFilePath     - Input file path*
* -DataSource        - Input Data Source CSDF_IB/CSDF_INTERSIGHT*
* -DataFormat        - Input Data Format CSDF_IB/CSDF_INTERSIGHT*
* -WorkerThreadCount - Input Worker Thread Count
* -OutputFilePath    - Output file path

PAS Engine Output will be written in the OutputFilePath specified in JSON format

```
./bin/profiler -InputFilePath=test_sample_data/CSDF_INTERSIGHT_100632_1613538186067796000.zip -DataSource=CSDF_INTERSIGHT -DataFormat=CSDF_INTERSIGHT

cat output.json 
[...]

```

### Library
#### Profiler
```
     // Initialize Profiler
     profiler.RegisterInputReaderFactory(inputreader.InputReaderFactory)
	 profiler.RegisterDevicePackageFactory(devicepackage.DevicePackageFactory)
	 inputProfiler := &profiler.ConcurrentProfiler{
	                    WorkerThreadCount: 1,
	                   },
     neFilter := func(neId string) bool {
		// NO filtering
		return true
	}

	// Profile Raw DeviceData to ProfiledDeviceData
	if profiledDeviceDataList, err = inputProfiler.ProfileCollectionData(metadata, inventoryFilePath, neFilter); err != nil {
		logger.ServiceLog.Errorf("Failed to Profile Inventory file %v, Reason %v", inventoryFilePath, err)
		return nil, err
	}

``` 
##  Post Processing
###  De-Dup Logic
- Create a map by grouping managed devices with managedNeId as key and array of ProfiledDeviceData as value to identify duplicates.
- If the length of value in above map is > 1, then there is a duplicate device with same managedNeId.
- Remove/ De-duplicate the duplicate devices entry by considering only the first element in the value of the map and recreate the map.
- Return the main array of ProfiledDeviceData using the recreated map.
### DCN Post Processor
RegisteredDeviceMOID from ne.json is the identifier to indicate which assets are in the same APIC “cluster”.
You will need this in order to populate the “Controller” value for each asset.  Here is the logic that has been agreed to:
-	Within a RegisteredDeviceMOID, get list of IPAddress where deviceType=controller.
-	Choose one IP (recommend we use lowest IP) to be the cluster/controller “IP”
-	Assign every asset in that RegisteredDeviceMOID with controller value of the select IP Address.
-   IP Address of Controller (APIC) with lowest IP needs to be mapped to its corresponding leafs, spines and other controllers that share the same  RegisteredDeviceMOID .
-   This controller IP Address will be assigned as mgmtSystemAddr and set to each devices' additional properties.
###  DCC Post Processor
- In Post Processing the profiledDeviceData received from dcc DP will be processed further based on clusterMoId.
- The Equipments in an Equipment Array of a device will be grouped based on clusterMoId.
- Once grouped, the lowest IP or Hostname  of its respective  NE will be identified.
- Identified NE's managedNeId will be assigned to all other NEs of the same device.


