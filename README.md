# Starve-Free-Reader-Writer

The readers-writers problem is a classical one in computer science. Here, we have a resource that can be accessed by readers, who do not modify the resource,
 and writers, who can modify the resource. When a writer is modifying the resource, no-one else can access it at the same time- another writer could corrupt
 the resource, and another reader could read a partially modified value. This problem is actually of three types:

(1) Readers priority - When there is at least one reader currently accessing the resource, allow new readers to access it as well. This can cause starvation
if there are writers waiting to modify the resource and new readers arrive all the time, as the writers will never be granted access as long as there is 
atleast one active reader.

(2) Writers priority - Here, readers may starve. 

(3) No priority - All readers and writers will be granted access to the resource in their order of arrival. If a writer arrives while readers are accessing
the resource, it wait until those readers free the resource and then modify it. New readers arriving in the meantime will have to wait.

For the third case i.e. we don't want starvation to happen and thus don't want to give anyone priority. For that the variables and functions required are :
-> Semaphore mutex (It is used ensure mutual exclusion to update readcount and writecount variables)
->resource (mutual exclusion semaphore to chech if resource is available or not)
-> wait() - decrements the semaphore value
-> signal() - increments the semaphore value
