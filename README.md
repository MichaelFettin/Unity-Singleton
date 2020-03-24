# Unity Singleton
A simple implementation of the singleton pattern with Generics.

## Usage
Create a new script (e.g. `GameManger`) and replace `MonoBehaviour` with `MonoBehaviourSingleton<GameManger>`. Calling `Instance` property will find the singleton gameobject in the scene at that moment. When loading another scene, the singleton will be destroyed as normal and set `Instance` to null. Calling `Awake()` will create a new `Instance` of the singleton. 

Sample method call: (e.g. `YourCreatedMethod()`) from `GameManger` via `GameManger.Instance.YourCreatedMethod();`.

**Awake() & OnDestroy()**
The methods `Awake()` and `OnDestory()` are both private protected virtual. You can call the methods in the `GameManger` class like so:

```
public class GameManager : MonoBehaviourSingleton<GameManager>
{
    private protected override void Awake()
	{
        base.Awake();

        // Your code here...
    }

    private protected override void OnDestroy()
	{
        base.OnDestroy();

        // Your code here...
    }

    // ...
}
```

## License 

This software is licensed under the MIT License. See the [license file](LICENSE) for details.  