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
 
#### Multi Chassis Usecase:
* In order to determine the Managed NE in case of Multi Chassis the stack-json is used.
* From each ne-json serialNumber is extracted and this serialNumber is mapped with the  stack-json to find the role applicable for given serialNumber.
* If the Role is MASTER for a given serialNumber then that NE will be considered as Managed Ne and other NEs will be Sub NE.


#### Data Model : DCN1A
Note : This section include new attributes added in avro schema for DCN1A 

| Attributes | Tags | Data Type | Description |
| ---------- | ---- | --------- | ----------- |
| FabricId | Inventory | string | Fabric Id field value |
| FabricName | Inventory | string | Fabric Name field value |
| PodId | Inventory | string | Pod Id field value |
| SiteName | Inventory | string | Site Name field value |
| Vendor | Inventory | string | Vendor field value |
| PartNumber | Inventory | string | Part Number field value |
| LastRebootTime | Inventory | long | Last Reboot Time field value |
| Controller | Inventory | string | Controller  field value |
