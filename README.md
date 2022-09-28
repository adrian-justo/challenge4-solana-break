# challenge4-solana-break

> Jot down the various differences between the way transactions are created in the Hello World example vs the Break example. Explore the accounts being used in the repository as well and create a brief - short write-up with your observations.
### Observations
Both programs have almost the same flow for creating transactions and accounts. Of course, the Break example is built more robust and secure than Hello World with the handling of connections, blockhash, keypairs, and such.

The key differences I have observed is that in the Hello World example transactions are created using `TransactionInstruction` either via `SystemProgram.createAccountWithSeed` or a new instance of it then processed using `sendAndConfirmTransaction` while in the Break example transactions are created by `CreateTransactionRPC` via `createTransaction` then processed by `WebSocket` via `send` and `Dispatch`.

For Accounts, they are used almost the same. In Hello World, it is derived from payer public key and seed provided then used as parameter for the program. In Break, it is being handled by `TransactionDetails` to be used for the program as well.