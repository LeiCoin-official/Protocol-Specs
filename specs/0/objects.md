
Container
```ts
class Container {
    public encodeToHex(forHash = false)
}
```

HashableContainer
```ts
abstract class HashableContainer extends Container {
    public calculateHash() {
        sha256(this.encodeToHex(forHash = true));
    }
}

```


Block
```ts

```

