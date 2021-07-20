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

### Data Model : DCC Subscription
Note : This section include new attributes added in parquet_ne.go and parquet_ne_subscription.go

#### 1- parquet_ne.go

 Attributes | Data Type | Description |
| ---------- | --------- | ----------- |
| EndCustomerGuId | string | End Customer GuId field value |
| EndCustomerGuName | string | End Customer GuName field value |
| LicenseLevelSummaryView | string | License Level Summary View field value |

#### 2- parquet_ne_subscription.go

| Attributes | Data Type | Description |
| ---------- | --------- | ----------- |
| CoverageStatus | string | Coverage Status field value |
| ServiceProgram | string | Service Program field value |
| ContractNumber | string | Contract Number field value |
| ServiceLevel | string | Service Level field value |
| ServiceLevelDescription | string | Service Level Description field value |
| TermEndDate | long | Term End Date field value |
| TermStartDate | long | Term Start Date field value |
| SubscriptionType | string | Subscription Type field value |
| TermsAndContentCd | string | Terms And Content Cd field value |
| SubscriptionCreateDate | long | Subscription Create Date field value |
| SubscriptionStatus | string | Subscription Status field value |
| SubscriptionReferenceId | string | Subscription Reference Id field value |
| SubscriptionBillToSiteUseCustName | string | Subscription Bill To Site Use Cust Name field value |
| SubscriptionBillToSiteUseId | long | Subscription Bill To Site Use Id field value |
| SubscriptionProductClass | string | Subscription Product Class field value |
| SubscriptionProductQuantity | long | Subscription Product Quantity field value |
| EndCustomerGuAddressLine1 | string | End Customer Gu Address Line1 field value |
| EndCustomerGuAddressLine2 | string | End Customer Gu Address Line2 field value |
| EndCustomerGuAddressLine3 | string | End Customer Gu Address Line3 field value |
| EndCustomerGuAddressLine4 | string | End Customer Gu Address Line4 field value |
| EndCustomerGuCityName | string | End Customer Gu City Name field value |
| EndCustomerGuState | string | End Customer Gu State field value |
| EndCustomerGuPostalCd | string | End Customer Gu Postal Cd field value |
| EndCustomerGuCountry | string | End Customer Gu Country field value |
| PartnerBeGeoId | long | Partner Be Geo Id field value |
| PartnerBeGeoName | string | Partner Be Geo Name field value |
| PartnerBeName | string | Partner Be Name field value |
| PartnerBeId | long | Partner Be Id field value |
| MonetizationTypeCd | string | Monetization Type Cd field value |
| ContractEntitlementDescr | string | Contract Entitlement Descr field value |
| LicenseTermInMonth | long | License Term In Month field value |
| WebOrderId | string | Web Order Id field value |
| ErpSalesOrderNumber | long | Erp  Sales Order Number field value |
