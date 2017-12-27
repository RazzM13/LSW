# LSW - Local Structured Web
A 3D geospatial database model for storing, organising and manipulating structured data.

In LSW units of data, also known herein as caches, are organized within a hierhical namespace structure that consists of static predefined sections (e.g. `/schemas`) or dynamically generated sections based on a derivative [Geohash-36](https://en.wikipedia.org/wiki/Geohash-36) algorithm that augments the original by providing support for scopes and will be referenced herein as *Scoped Geohash-36* and, in short form, *SGeohash*.

### Scoped Geohash-36
The Scoped Geohash-36 algorithm relies upon the original definition for representing 2D world coordinates without support for checksuming or altitude representation; instead, a new concept of *scope* is introduced. A scope can be construed as a delineation of spatial representation such that a geohash value in one scope does not identify with the same value within another scope (i.e. [alternative universes](https://en.wikipedia.org/wiki/Multiverse)).

The syntax for expressing a geohash value referencing a particular scope is the following: `geohash@scope`; the `geohash` part is any valid Geohash-36 string having a maximum size of 10 bytes, whilst the `scope` part is any valid UTF-8 string, including NULL, having a maximum size of 13 bytes (e.g. `BK5q7PHG2H@1989`). SGeohash values are also permitted the cannonical geohash form, without the `@scope` suffix, however, they must be regarded as `geohash@` when processed (i.e. geohash value with a NULL scope).

### Caches
A cache is the basic unit of data within LSW, it comprises of a data property and a metadata property. The data property acts as a container for structured data that is formatted according to a predefined schema; the previously mentioned schema pertains to the metadata property of the cache, more specifically to the value of it's `type` key.

Upon the creation of a cache, the metadata property members are initialized and the following become immutable: `id`, `type`, `created_at`. For a full description of the metadata property members, please consult the following table:

Key         | Description of Value
----------- | --------------------
id          | A unique identifier that describes a specific cache within the given namespace.
type        | A unique identifier that references a specific cache within the SCHEMA namespace.
created_at  | The UNIX-timestamp representation of the moment at which the cache had been created.
modified_at | The UNIX-timestamp representation of the moment at which the cache had been last modified.

Caches can be categorised based on their designation within the LSW namespace:

Cache type  | Namespace path                | Description of Parameters
----------- | ----------------------------- | -----------
SchemaCache | /schemas/{username}/{cacheid} | {username} and {cacheid} are human-friendly identifiers that reference a specific user and a specific SchemaCache, respectively.
GlobalCache | /globals/{username}/{cacheid} | {username} and {cacheid} are human-friendly identifiers that reference a specific user and a specific GlobalCache, respectively.
AppCache    | /apps/{username}/{cacheid}    | {username} and {cacheid} are human-friendly identifiers that reference a specific user and a specific AppCache, respectively.
GeoCache    | /{sgeohash}/{cacheid}         | {sgeohash} is a Scoped Geohash-36 value whilst, {cacheid} is a machine generated, globally unique identifier (GUID) that references a specific GeoCache.

### Reserved namespaces

### Schema caches
A SchemaCache is a type of cache that is in itself an instance of `/schemas/LSW/SchemaCache` and contains a [JSON Schema](http://json-schema.org/) document, which is used by other caches as a blueprint to describe and structurally validate data. In contrast to all other cache types, once created, the SchemaCache can no longer be modified; this design decision has been taken to prevent caches that have been created prior to the alteration of their respective schema from becoming invalid.

### Global caches
A GlobalCache is a type of cache that is created with the purpose of preventing data duplication and simplifying management of shared information, it can be an instance of any of the caches registered under the `/schemas` namespace and should be used as a common resource, by referencing, whenever the need arrises to publish the same information in multiple caches.

Data duplication is an important matter in any large-scale database system, that stems from the underlying need for data sharing and correlation and is especially prevalent in key-value stores; from an LSW perspective, data duplication might occur between caches due to a common trait such as authorship information or a shared resource.

### Application caches
### Geospatial caches
A GeoCache is a type of cache that resides at a given SGeohash location, under an automatically generated [GUID](https://www.ietf.org/rfc/rfc4122.txt), within the LSW namespace (e.g. `/BK5q7PHG2H@1989/6c84fb90-12c4-11e1-840d-7b25c5ee775a`) and it can be an instance of any of the caches registered under the `/schemas` namespace.

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
