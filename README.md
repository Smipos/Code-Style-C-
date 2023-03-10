# Code Style C#
Соглашения о написании кода на C#

## Регистр Pascal
##### Используйте регистр pascal ("PascalCasing") при именовании **class**, **record** или **struct**.
```
public class DataService 
{
}
```
```
public record PhysicalAddress(
    string Street,
    string City,
    string StateOrProvince,
    string ZipCode);
```
```
public struct ValueCoordinate
{
}
```
##### При присвоении interface имени используйте регистр pascal в дополнение к префиксу имени с помощью **I**. Это явно указывает потребителям, что это **interface**.
```
public interface IWorkerQueue
{
}
```
##### При именовании public членов типов, таких как поля, свойства, события, методы и локальные функции, используйте регистр pascal.
```
public class ExampleEvents
{
    // A public field, these should be used sparingly
    public bool IsValid;

    // An init-only property
    public IWorkerQueue WorkerQueue { get; init; }

    // An event
    public event Action EventProcessing;

    // Method
    public void StartEventProcessing()
    {
        // Local function
        static int CountQueueItems() => WorkerQueue.Count;
        // ...
    }
}
```
##### При записи позиционных записей используйте регистр pascal для параметров, так как они служат общедоступными свойствами записи.
```
public record PhysicalAddress(
    string Street,
    string City,
    string StateOrProvince,
    string ZipCode);
```
## Регистр camelCasing
##### Используйте верблюдьий регистр ("camelCasing") при именовании **private полей** и **internal** примените к ним префикс  **_**.
```
public class DataService
{
    private IWorkerQueue _workerQueue;
}
```
##### При работе с **полями static**, которые являются **private** или **internal**, используйте **s_** префикс, а для статического потока  используйте **t_**.
```
public class DataService
{
    private static IWorkerQueue s_workerQueue;

    [ThreadStatic]
    private static TimeSpan t_timeSpan;
}
```
##### При написании параметров метода используйте регистр верблюда.
```
public T SomeMethod<T>(int someNumber, bool isValid)
{
}
```
