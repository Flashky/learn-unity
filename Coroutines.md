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
  yield return new WaitForSeconds(3);
  // Insert your code for doing anything after the wait is over.
}
```

### Alive execution routine

An alive execution routine will run forever until being told to stop.

```C#
IEnumerator MyAliveCoroutine() {
  while(true) {
    // Insert your code for doing anything.
    yield return new WaitForSeconds(3);
    // Insert your code for doing anything after the wait is over.
  }
}
```

## Starting a coroutine execution

Use the ``StartCoroutine(<your_coroutine>())`` method for starting the coroutine execution.

Example:

```C#
private void Update()
{
    Coroutine myCoroutineReference = StartCoroutine(MyCoroutine());
}
```

We can retrieve the coroutine reference to stop it later on.

## Stoping a coroutine

### Stop all coroutines

```C#
private void Update()
{
    // Two coroutines are started
    StartCoroutine(MyCoroutine());
    StartCoroutine(MyAliveCoroutine());
    
    // [...]
    
    // Later on, stop all the coroutines.
    StopAllCoroutines();
    
    // Both MyCoroutine and MyAliveCoroutine will be stopped
}
```

### Stop a specific coroutine

```C#
private void Update()
{
    // Two coroutines are started, we pick the reference of one of them
    StartCoroutine(MyCoroutine());
    Coroutine myAliveCoroutineReference = StartCoroutine(MyAliveCoroutine());
    
    // [...]
    
    // Later on, stop the specific coroutine:
    StopCoroutine(myAliveCoroutineReference);
    
    // Only MyAliveCoroutine will be stopped
}
```

## Yield conditions

There are several yield conditions that can be applied.

### WaitForSeconds(float)

The most basic and easy to use. It will wait for the specified number of seconds before continuing the execution:

```C#
yield return new WaitForSeconds(2f);
```

### Wait on another coroutine to finish

This will allow us start coroutines from within coroutines. The main coroutine will wait for the secondary coroutine to finish before continuing:

```C#
yield return StartCoroutine(MyOtherCoroutine());
```

