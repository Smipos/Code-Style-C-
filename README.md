# Code Style C#
Соглашения о написании кода на C#

## Регистр Pascal
#####Используйте регистр pascal ("PascalCasing") при именовании **class**, **record** или **struct**.
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
#####При присвоении interfaceимени используйте регистр pascal в дополнение к префиксу имени с помощью **I**. Это явно указывает потребителям, что это **interface**.
```
public interface IWorkerQueue
{
}
```
При именовании public членов типов, таких как поля, свойства, события, методы и локальные функции, используйте регистр pascal.

C#

Копировать
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
При записи позиционных записей используйте регистр pascal для параметров, так как они служат общедоступными свойствами записи.

C#

Копировать
public record PhysicalAddress(
    string Street,
    string City,
    string StateOrProvince,
    string ZipCode);
