<h1>Asymptotic Analysis<h1>

<h2>Comparing the ArrayListDeque and the ArrayDeque implementations<h2>

ArrayListDeque
  addFirst()
  - Best case: Θ(N) because all of the elements in the array have to shift to the right in order to insert a new element in the beginning.
  - Worst case: Θ(N) because it does not matter what is being inserted, all of the elements still
  have to shift to the right of the array in order to insert something new at the beginning.

  addLast()
  - Best case: Θ(1) because there might be space at the end of an array to insert a new element
  without needing to increase the capacity.
  - Worst case: Θ(N) because the array might not have space at the end and therefore the capacity
  would have to be increased, meaning each element would have to be moved to the new array with
  increased capacity one by one.

  removeFirst()
  - Best case: Θ(N) because similarly to addFirst, we would need to shift all of the elements in the array to the left 1 so there isn’t an unassigned index at the beginning of the array.
  - Worst case: Θ(N) because no matter what the input is, all elements of the array must shift
  down 1 in order to avoid an unassigned index at the start of the array.

  removeLast()
  - Best case: Θ(1) because there is no need to shift the remaining elements in either direction,
  there can be empty storage at the end of the array.
  - Worst case: Θ(1) because irrespective of input, we are allowed to have empty space at the end
  of the array. There is no need to shift the elements in either direction.

ArrayDeque
  addFirst()
  - Best case: Θ(1) because the deque data structure allows us to add an element to the front of
  the array by just linking that element to the element that was in front previously, and shifting
   the front pointer to the new element.
  - Worst case: Θ(N) because in the case the array is full storage needs to be increased, all of
   the elements of the current array need to be copied over.

  addLast()
  - Best case: Θ(1) because given that there is enough storage, the new element is simply appended
   to the back of the array.
  - Worst case: Θ(N) because in the case of a full array, the storage needs to be increased, and
   all of the elements need to be copied into the new array.

  removeFirst()
  - Best case: Θ(1) because to remove from the front we simply have to remove a reference to the
   node at the beginning of the array. No need to shift the elements at all.
  - Worst case: Θ(N) because we might need to decrease the capacity of the array, meaning that we
   would have to copy the elements over to a new (smaller) array.

  removeLast()
  - Best case: Θ(1) because we would simply have to remove the reference to the node at the back
   of the array. There is no need to shift the elements.
  - Worst case: Θ(N) because we might need to decrease the capacity of the array, meaning that we
   would have to copy the elements over to a new (smaller) array.

These graphs represent the runtime for the addLast() method
Here we can see that the plot for the LinkedDeque graph has by far the smallest slope out of the
three. When it comes to the asymptotic analysis of these 3 implementations, the slope is an
indication of how much the runtime will increase with bigger and bigger inputs.
I used the line of best fit represented by y = mx + b to compare across the three graphs.
The graph with the steepest slope is ArrayListDeque, followed by ArrayDeque, and finally
LinkedDeque.

I tested a couple of different methods to show the difference in ArrayListDeque and ArrayDeque, but
I think the one that shows the difference the most is removeFirst() method.
Here we can see that in the ArrayListDeque the slope is much bigger. This reflects how different the runtime is for these two methods.
As the number of our input increases towards infinity, the runtime for the removeFirst() method in ArrayList increases really quickly, almost in a linear manner. This makes sense according to our theoretical asymptotic analysis which gave us a theta bound of Θ(N) in both the best case and worst
case. We can see however, in the ArrayDeque graph that the runtime pretty much stays constant no
matter how many inputs are there.
