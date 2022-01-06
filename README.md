# NFT Series Implementation

# WARNING

This repository is **not** up-to-date with the current NFT [standards](https://nomicon.io/Standards/NonFungibleToken/README.html). For an example repository that is currently being maintained and is up-to-date see the [nft-tutorial](https://github.com/near-examples/nft-tutorial) repository.

## Rough notes on token series (type) and editions

```
// Mappings pseudo code
TokenTypeString -> TokenTypeInt
TokenTypeInt -> TokenTypeStruct (data)

TokenId.split(":")[0] -> TokenTypeInt
TokenId.split(":")[1] -> TokenEditionInt (unique token in type)


In Rust:
// getting owner of token
let owner_id = self.tokens.owner_by_id.get(&token_id)

// getting metadata for token (TokenTypeStruct)
let mut token_id_iter = token_id.split(TOKEN_DELIMETER);
let token_type_id = token_id_iter.next().unwrap().parse().unwrap();
let metadata = self.token_type_by_id.get(&token_type_id).unwrap().metadata;
```

## Instructions

`yarn && yarn test:deploy`

#### Pre-reqs

Rust, cargo, near-cli, etc...
Everything should work if you have NEAR development env for Rust contracts set up.

[Tests](test/api.test.js)
[Contract](contract/src/lib.rs)
