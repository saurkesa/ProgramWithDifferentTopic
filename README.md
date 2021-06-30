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
 
 
| Attributes | Tags | Data Type | Description |
| ---------- | ---- | --------- | ----------- |
| assetType | Inventory | string | Type of asset : Hardware / Software |
| profileName | Inventory | string | Profile Name field value |
| hclStatus | Inventory | string | Hcl Status field value |
| ucsDomain | Inventory | string | Ucs Domain field value |
| hxClusterName | Inventory | string | Hx Cluster field value |
| portalUrl | Inventory | string | Portal Url field value |
| managementMode | Inventory | string | Management mode of the device - UCSM, IntersightStandalone, Intersight |
| modTime | Inventory | long | Mod time field value |
| accountMoid | Inventory | string | Account Moid field value |
| connectionStatus | Inventory | string | Connection Status field value |
| connectionStatusChangeTime | Inventory | long | Connection status change time field value |
| ucsdStatus | Inventory | string | Ucsd status licensing field value |
| ucsdLicenseInfoMoid | Inventory | string | Ucsd License Info field value |
| intersightLicenseStatus | Inventory | string | Intersight License Status field value |
| intersightLicenseLevel | Inventory | long | Intersight License Level field value |
| parentMoid | Inventory | string | Parent Moid field value |
| moid | Inventory | string | Moid field value |
| clusterMoid | Inventory | string | Cluster Moid field value | 
| platformType | Inventory | string | Platform Type field value |
| intersightTags | Inventory | array | The tag entry. This contains both user and system defined tag  values. |


