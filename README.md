Counter example in Rust
=================================

[![Open in Gitpod!](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/rust-counter)

<!-- MAGIC COMMENT: DO NOT DELETE! Everything above this line is hidden on NEAR Examples page -->

## Description

This contract implements simple counter backed by storage on blockchain.
But with usage of your tokens.
Contract in `contract/src/lib.rs` provides methods to increment / decrement counter and get it's current value or reset.
When you increment - you give yours tokens to contract. When you decrement - some tokens are transferred to you. 
UPDT: It also checks if someone have already taken Token so it won't give it more then once for one account.
Also it's now impossible to decrement counter below zero. 


Plus and minus buttons increase and decrease value correspondingly. When button L is toggled, a little light turns on, just for fun. RS button is for reset. LE and RE buttons to let the robot wink at you.

## To Run
Open in the Gitpod link above or clone the repository.

```
git clone https://github.com/near-examples/rust-counter
```


## Setup [Or skip to Login if in Gitpod](#login)
Install dependencies:

```
yarn
```

If you don't have `Rust` installed, complete the following 3 steps:

1) Install Rustup by running:

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

([Taken from official installation guide](https://www.rust-lang.org/tools/install))

2) Configure your current shell by running:

```
source $HOME/.cargo/env
```

3) Add wasm target to your toolchain by running:

```
rustup target add wasm32-unknown-unknown
```

Next, make sure you have `near-cli` by running:

```
near --version
```

If you need to install `near-cli`:

```
npm install near-cli -g
```

## Login
If you do not have a NEAR account, please create one with [NEAR Wallet](https://wallet.testnet.near.org).

In the project root, login with `near-cli` by following the instructions after this command:

```
near login
```

Modify the top of `src/config.js`, changing the `CONTRACT_NAME` to be the NEAR account that was just used to log in.

```javascript
…
const CONTRACT_NAME = 'YOUR_ACCOUNT_NAME_HERE'; /* TODO: fill this in! */
…
```

Start the example!

```
yarn start
```

## To Test

```
cd contract
cargo test -- --nocapture
```

## To Explore

- `contract/src/lib.rs` for the contract code
- `src/index.html` for the front-end HTML
- `src/main.js` for the JavaScript front-end code and how to integrate contracts
- `src/test.js` for the JS tests for the contract

## To Build the Documentation

```
cd contract
cargo doc --no-deps --open
```
