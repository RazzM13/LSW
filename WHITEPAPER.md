# LSW - Local Structured Web
A 3D geospatial database model for storing, organising and manipulating structured data.

## Data types
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
