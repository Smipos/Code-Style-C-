# Code Style C#
Соглашения о написании кода на C#

## Регистр Pascal
Используйте регистр pascal ("PascalCasing") при именовании class, recordили struct.
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
