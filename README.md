<a href="readme"></a>Use safe refs to hold references to Unity components that may be destroyed. An instance of SafeRef<MyComponent>.value will be null if the component or its GameObject has been destroyed.

````c#
MyComponent someComponent = GetComponentsInChildren<MyComponent>();
var ref = new SafeRef<MyComponent>(someComponent);
// ref.value will return someComponent
Destroy(someComponent.gameObject);
// ref.value will return null
````
