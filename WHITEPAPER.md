# LSW - Local Structured Web
A 3D geospatial database model for storing, organising and manipulating structured data.

In LSW units of data, also known herein as caches, are organized within a hierhical namespace structure that consists of static predefined sections (e.g. `/schemas`) or dynamically generated sections based on a derivative [Geohash-36](https://en.wikipedia.org/wiki/Geohash-36) algorithm that augments the original by providing support for scopes and will be referenced herein as *Scopped Geohash-36* and, in short form, *sgeohash*.

### Scopped Geohash-36
The Scopped Geohash-36 algorithm relies upon the original definition for representing 2D world coordinates without support for checksuming or altitude representation; instead, a new concept of *scope* is introduced. A scope can be construed as a delineation of spatial representation such that a geohash value in one scope does not identify with the same value within another scope (i.e. [alternative universes](https://en.wikipedia.org/wiki/Multiverse)).

The syntax for expressing a geohash value referencing a particular scope is the following: `geohash@scope`; the `geohash` part is any valid Geohash-36 string having a maximum size of 10 bytes, whilst the `scope` part is any valid UTF-8 string having a maximum size of 13 bytes (e.g. `BK5q7PHG2H@1989`).

### Caches
A cache is the basic unit of data within LSW, it comprises of a data property and a metadata property. The data property acts as a container for structured data that is formatted according to a predefined schema; the previously mentioned schema pertains to the metadata property of the cache, more specifically to the value of it's `type` key.

Upon the creation of a cache, the metadata property members are initialized and the following become immutable: `id`, `type`, `created_at`. For a full description of the metadata property members, please consult the following table:

Key         | Description of Value
----------- | --------------------
id          | A unique identifier that describes a specific cache within the given namespace.
type        | A unique identifier that describes a specific cache within the SCHEMA namespace.
created_at  | The UNIX-timestamp representation of the moment at which the cache had been created.
modified_at | The UNIX-timestamp representation of the moment at which the cache had been last modified.

Caches can be categorised based on their role within the LSW:
- 

### Schemas

## Data types
## Data structure
## Data manipulation

### 

    Copyright 2017 @RazzM13
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
