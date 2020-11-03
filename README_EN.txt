* README_EN.txt
* 2020.11.03
* tacklelib--3dparty--rapidyaml

1. DESCRIPTION
2. LICENSE
3. REPOSITORIES
4. INSTALLATION
5. AUTHOR

-------------------------------------------------------------------------------
1. DESCRIPTION
-------------------------------------------------------------------------------
rapidyaml patched sources fork from:
https://github.com/biojppm/rapidyaml

From authors:

  Or ryml, for short. ryml is a library to parse and emit YAML, and do it fast.

  ryml parses both read-only and in-situ source buffers; the resulting data
  nodes hold only views to sub-ranges of the source buffer. No string copies or
  duplications are done, and no virtual functions are used. The data tree is a
  flat index-based structure stored in a single array. Serialization happens
  only at your direct request, after parsing / before emitting. Internally the
  data tree representation has no knowledge of types (but of course, every node
  can have a YAML type tag). It is easy and fast to read, write and iterate
  through the data tree.

  ryml can use custom per-tree memory allocators, and is exception-agnostic.
  Errors are reported via a custom error handler callback. A default error
  handler implementation using std::abort is provided, but you can opt out, or
  provide your exception-throwing callback.

  ryml has respect for your compilation times and therefore it is NOT
  header-only. It uses standard cmake build files, so it is easy to compile and
  install.

  ryml has no dependencies, not even on the STL (although it does use the
  libc). It provides optional headers that let you serialize/deserialize STL
  strings and containers (or show you how to do it).

  ryml is written in C++11, and is known to compile with:

  * Visual Studio 2015 and later
  * clang++ 3.9 and later
  * g++ 5 and later

The original library patched to fix these issues:

1. Use std::is_trivially_copyable in GCC major version less than 5:
   ``is_trivially_copyable` is not member of `std` (GCC < 5)``:
   https://github.com/biojppm/rapidyaml/issues/70

2. Use std::align in GCC major version less than 5:
   `std::align not supported by g++4.9`:
   https://stackoverflow.com/questions/27064791/stdalign-not-supported-by-g4-9

-------------------------------------------------------------------------------
2. LICENSE
-------------------------------------------------------------------------------
Copyright (c) 2018, Joao Paulo Magalhaes <dev@jpmag.me>
(see included text file "LICENSE.txt" or
https://github.com/biojppm/rapidyaml/blob/master/LICENSE.txt)

-------------------------------------------------------------------------------
3. REPOSITORIES
-------------------------------------------------------------------------------
Primary:
  * https://sf.net/p/tacklelib/3dparty--rapidyaml/HEAD/tree/branches
    https://svn.code.sf.net/p/tacklelib/3dparty--rapidyaml/branches
First mirror:
  * https://github.com/andry81/tacklelib--3dparty--rapidyaml/tree/branches
    https://github.com/andry81/tacklelib--3dparty--rapidyaml.git
Second mirror:
  * https://bitbucket.org/andry81/tacklelib-3dparty-rapidyaml/src/branches
    https://bitbucket.org/andry81/tacklelib-3dparty-rapidyaml.git

-------------------------------------------------------------------------------
4. INSTALLATION
-------------------------------------------------------------------------------
N/A

-------------------------------------------------------------------------------
5. AUTHOR
-------------------------------------------------------------------------------
Andrey Dibrov (andry at inbox dot ru)
