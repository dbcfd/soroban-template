# {{project-name}}
Soroban contract. For more information, see [Soraban](https://soroban.stellar.org/docs/).

## Setting up Soroban
If you don't already have the wasm32 target, you will need to add it

    rustup target add wasm32-unknown-unknown

You can then install the Soroban client

    cargo install --locked --version 0.2.1 soroban-cli

## Testing
To test your contract locally

    cargo test

## Deploying the Contract
First, you will need to build your contract

    cargo build --target wasm32-unknown-unknown --release

You can then deploy your contract with

    soroban invoke \
      --wasm target/wasm32-unknown-unknown/release/{{project-name}}.wasm \
      --id 1 \
      --fn hello \
      --arg friend
