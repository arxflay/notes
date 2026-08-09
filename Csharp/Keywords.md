`out` keyword - similar to returning multiple values or to creating variables and passing them with ref
```csharp
void x(out int a, out int b)
{
	a = 20;
	b = 30;
}
x(out int valueA, out int valueB)
```