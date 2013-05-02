# Proboscis

**A new meta-framework for RPC.**

## Transports

### PoTCP

The Proboscis over TCP (PoTCP) transport is based off of the [Netstring][netstring]/[Bencode][bencode] formats.

  [netstring]: http://en.wikipedia.org/wiki/Netstring
  
  [bencode]: http://en.wikipedia.org/wiki/Bencode

#### Request

  {method}.{format}:{length}:{data}

#### Response

  {status}:{format}:{length}:{data}

## License

The specification of Proboscis (this document and all accompanying documents and code) is released into the public domain according to the [Creative Commons Zero 1.0](http://creativecommons.org/publicdomain/zero/1.0/) license.
