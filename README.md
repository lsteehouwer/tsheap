# Typescript Heap
Implementation of a heap datastructure in Typescript. Supports both min-heaps and max-heaps.

## Creation
A heap is an Implementation of a priority queue. You can insert any sort of object in the heap, so long all the elements are off the same type. You need to supply a comparison function that is used for restoring the heap property.

The following example creates a min-heap of numbers.
```typescrpt
let heap = new Heap<number>( (lhs, rhs) => {
    if(lhs == rhs) return 0;
    else if(lhs < rhs) return 1;
    else return -1;
});
```
To make it max-heap, just flip the `1` and `-1` in the comparison function.

## Insertion
You can insert elements with the `insert` method.
```typescript
let heap = new Heap<number>( (lhs, rhs) => {
    if(lhs == rhs) return 0;
    else if(lhs < rhs) return -1;
    else return 1;
});
heap.insert(5);
```

## Extraction
You can extract the element with the most priority from the heap using the `extract` method.
```typescript
let heap = new Heap<number>( (lhs, rhs) => {
    if(lhs == rhs) return 0;
    else if(lhs < rhs) return -1;
    else return 1;
});
heap.insert(2);
heap.extract(); // => 2
```

## Querying
You can retrieve the amount of elements in the heap by using the `size` method
```typescript
let heap = new Heap<number>( (lhs, rhs) => {
    if(lhs == rhs) return 0;
    else if(lhs < rhs) return -1;
    else return 1;
});
heap.insert(1);
heap.insert(2);
heap.insert(3);
heap.size(); // => 3
```
You can also determine whether the heap is empty using the `isEmpty` method
```typescript
let heap = new Heap<number>( (lhs, rhs) => {
    if(lhs == rhs) return 0;
    else if(lhs < rhs) return -1;
    else return 1;
});
heap.insert(1);
heap.isEmpty(); // => false
heap.extract();
heap.isEmpty(); // => true
```

## Status
This data structure is pretty much finished. Some convenience methods may be missing
