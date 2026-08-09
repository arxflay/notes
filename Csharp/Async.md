`await` keyword - wait until method is completed only method is completed

`async` method works in that way that it will:
1) return to async method called in async method if it's completed. 
2) return to caller method if it can't continue
If async method is called inside another async method but await keyword is missing, then called method will run synchroniously.

Example: 
Async method A calls B, which returns to A because method calls B must wait 50ms, but method A also must wait 100ms, so after 50ms B will be resumed. When B finishes, we will wait for A until it's resumed. Because task B stored in task variable in A is finished, await will do nothing. If `await task` wouldn't be there, then A would wait until B is finished.
```csharp
async Task<int> B()
{
    await Task.Delay(50);
    Console.WriteLine("Hello3");
    return 10;
}

async Task A()
{
    var task = test2();
    await Task.Delay(100);
    await task;
    Console.WriteLine("Hello2");
    
}
```

Typical async result type (promise, similar to std::future) is `Task` for void or `Task<ResultType>` for non void async method
Async method can't accept ref (equivalent to C++ &) or out keyword

