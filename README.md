<a href="readme"></a>When components keep references to other components, it's easy to end up with null pointer problems. SafeRefs are a simple way to always know whether a component reference is valid.

## Install

From your unity project folder:

    npm init --force # only if you don't yet have a package.json file
    npm install --save beatthat/safe-refs

The package and all its dependencies will be installed under Assets/Plugins/packages.

In case it helps, a quick video of the above: https://youtu.be/Uss_yOiLNw8

## Usage

An instance of SafeRef<MyComponent>.value will be null if the component or its GameObject has been destroyed.

```csharp
MyComponent someComponent = GetComponentsInChildren<MyComponent>();
var ref = new SafeRef<MyComponent>(someComponent);
// ref.value will return someComponent
Destroy(someComponent.gameObject);
// ref.value will return null
```
