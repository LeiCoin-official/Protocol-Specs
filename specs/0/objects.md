
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
export class Block extends HashableContainer {
    public index: Uint64;
    public slotIndex: Uint64;
    public hash: Uint256;
    public previousHash: Uint256;
    public timestamp: Uint64;
    public minter: AddressHex;
    public signature: Signature;
    public body: BlockBody;
    public readonly version: PX = PX.A_00;
}

export class BlockBody extends Container {
    public transactions: Transaction[];
    public slashings: Slashing[];
}
```

Transaction:
```ts
export class Transaction extends HashableContainer {
    public txid: Uint256;
    public senderAddress: AddressHex;
    public recipientAddress: AddressHex;
    public amount: Uint64;
    public nonce: Uint64;
    public timestamp: Uint64;
    public input: Uint;
    public signature: Signature;
    public readonly version = PX.V_00;
}
```

