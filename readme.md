Metis-schemas
===

This repository provides all the data schemas relative to the metis experiment. There are meant to be used in different server-side and client-side applications. These are written according to the [JSON Schema 6](http://json-schema.org/specification.html) specification.

# Installation


```
npm install https://github.com/robindemourat/metis-schemas
```

# Usage

```
import schemas from 'metis-schemas'

const {
  Asset,
  User,
  Resource,
  Composition,
  Montage,
  Diffusion,
  Deliverable,
} = schemas;
```

You can then use these schemas for validation (for instance with [ajv](https://www.npmjs.com/package/ajv) module) or for creation of new standard objects (for instance with [json-schemas-defaults](https://github.com/chute/json-schema-defaults) module).

## JSON-schema custom properties for UI forms generation

Please note that the schemas are enriched with some non-standard custom properties aimed at facilitating their use for generating UI forms.

* `editable` (Boolean) : whether value can be edited when editing the object
* `longString` (Boolean) : whether UI should display a `textarea` instead of an `input` for a given property
* `anyOfFrom` (String) : when object is an `anyOf`, indicates the path of a value to look for (e.g. `metadata.resource_type`) in the edited object to determine what alternative to choose for the related subschema reference UI display.
* `accept_mimetypes` (Array of Strings) : for properties aimed at being displayed as a file input, determines which file types can be accepted

## Licenses

LGPL-3.0

CECCIL-C
