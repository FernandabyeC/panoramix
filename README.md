Panoramix
=========

This is an EVM decompiler.

It's is a fork of the Panoramix original repo that's not maintained actively by its author anymore: https://github.com/eveem-org/panoramix.git

The goal of this fork is to maintain Panoramix in a decent shape, fix some crashes, implement missing opcodes...
I also got rid of the "tilde" syntax that was using a custom python encoding and use vanilla Python instead. And I made it a proper python package that can be imported.
There is also a better support of timeouts, as instead of stopping entirely we will fallback and print whatever we decompiled even if it's not complete.

The code quality is still not great and the software is complex, it's mostly reserved for advanced users.

## Installation

```console
$ pip install panoramix-decompiler
```

## Running

You can specify a web3 provider using the environment variable `WEB3_PROVIDER_URI`. In this case a local provider was set.

```console
$ WEB3_PROVIDER_URI=http://localhost:7545 panoramix 0x71C7656EC7ab88b098defB751B7401B5f6d8976F
```

You can also provide the bytecode for decompilation.

```console
$ panoramix 6004600d60003960046000f30011223344
```

## Examples

I have decompiled all of mainnet, and make sure to decompile again on the latest Panoramix version from time to time.

You can access decompilations using Oko: https://OKX.ETH.com/

Here is an example for cryptokitties: https://oko.palkeo.com/0x06012c8cf97BEaD5deAe237070F9587f8E7A266d/code/

## Caveats

Windows is not supported currently.

## Changelog

### 0.5.0

 * Added support for the BASEFEE opcode.
 * Updated bytecode database / ABI definitions.
 * Ability to decompile the Solidity-generated Panic reverts.
 * Lots of simplification / code cleanup.
 * Moved to Poetry as the dependency management tool.
