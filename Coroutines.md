A coroutine is a fragment of code which will be executed by Unity engine, then put on a hold, and then continue its execution.

Coroutines **are not** multi-threading.

## Creating a coroutine

We can create two kind of coroutines:

- Single execution routine.
- Alive execution routine.

### Single execution routine

A single execution routine will run just once and finish until it is invoked once again. 
Somehow, is pretty similar to just calling any other method, but it will be able to have a wait. 
This is useful, for example, for playing death animations or similar things.

```C#
IEnumerator MyCoroutine() {
  // Insert your code for doing anything.
  WaitForSeconds(3);
  // Insert your code for doing anything after the wait is over.
}
```

### Alive execution routine

An alive execution routine will run forever until being told to stop.

```C#
IEnumerator MyAliveCoroutine() {
  while(true) {
    // Insert your code for doing anything.
    WaitForSeconds(3);
    // Insert your code for doing anything after the wait is over.
  }
}
```

## Starting a coroutine execution

Use the ```StartCoroutine(<your_coroutine>())`` method for starting the coroutine execution.

Example:

```C#
private void Update()
{
    Coroutine myCoroutineReference = StartCoroutine(MyCoroutine());
}
```

We can retrieve the coroutine reference to stop it later on.

## Stoping a coroutine

For stopping all the coroutines:

``
private void Update()
{
    StopAllCoroutines();
}
``

For stopping a specific coroutine, use its reference:

```C#
private void Update()
{
    // At some point, a coroutine was started and we have its reference
    Coroutine myCoroutineReference = StartCoroutine(MyCoroutine());
    
    // [...]
    
    // Later on, stop the specific coroutine:
    StopCoroutine(myCoroutineReference); // Immeditally
}
```
