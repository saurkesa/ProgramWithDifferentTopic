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
     
Binary search works on sorted arrays. Binary search begins by comparing an element in the middle of the array with the target value. If the target value matches the element, its position in the array is returned. If the target value is less than the element, the search continues in the lower half of the array.

Peak element: will be greater of both it neighbour element
note : for first and last element only one neighbour is there so they will check with that if it is greater then that will be peak element

Bitonic Array: An array is said to be bitonic if the elements in the array are first strictly increasing then strictly decreasing

Problem: search element in bitonic array
first find peak element then call two binary search tree and search element.
bst(0,peak-1,arr,element) bst(peak, arr.length-1,arr,element)
  




