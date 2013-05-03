# Proboscis 1.0-Alpha

**A new meta-framework for RPC.**

#### Nomenclature

*well-defined* indicates that something is known to both server and client.

## Transports

### PoTCP

The Proboscis over TCP (PoTCP) transport is based off of the [Netstring][netstring]/[Bencode][bencode] formats.

  [netstring]: http://en.wikipedia.org/wiki/Netstring
  
  [bencode]: http://en.wikipedia.org/wiki/Bencode

#### Request

    {method}.{format}:{length}:{data}

*method* is at least 1 ASCII character in the range `[0-9A-Za-z:/\-_]`. Any other characters are invalid.

*format* is either one of the standard Proboscis formats or a well-defined custom format (MIME types are acceptable).

*length* is a base-10 non-negative (zero allowed) integer indicating the number of bytes following the colon.

*data* is a sequence of *length* bytes.

#### Response

    {status}:{format}:{length}:{data}

*format* follows the same guidelines as a request *format*.

*status* follows the [HTTP status code](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes).

*length* and *data* follow the same guidelines as in a request.

## Formats

`text` Plain text

`json` JSON

`proto` Google Protocol Buffer (message must be well-defined)

`thrift` Apache Thrift (struct must be well-defined)

## License

The specification of Proboscis (this document and all accompanying documents and code) is released into the public domain according to the [Creative Commons Zero 1.0](http://creativecommons.org/publicdomain/zero/1.0/) license.
