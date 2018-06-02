Identifiers
-----------

Identifiers are really flexable they may contain hyphens "-" and plusses "+" and primes "'" and may even be made up of multiple words with spaces inbetween, see [Objects](/Reference_Manual/Talk/Object.md). Also AFAICT you will be able to be keywords as identifiers too.

They may also be any Unicode sequence but must be quoted if they do not follow the following rules.
  - They must begin with either an upper or lowercase alphabetical character
  - They may contain or end with with alphabetical or numeric characters
  - They may contain oer end with hyphens "-" and plusses "+" and primes "'"

Whitespace is the main delimiter for arithmetic expressions so, 'a-b' is an identifier 'a - b' is an expression. In definitions 'windows++' for an example maybe used as an identifier, see [Packages](/Reference_Manual/Package.md) for an example.
