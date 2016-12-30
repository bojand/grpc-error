# grpc-error

Utility Error class suitable for gRPC error responses

### Related

[create-grpc-error](https://github.com/bojand/create-grpc-error) - Just a class wrapper around
this module

## Usage

```js
const GRPCError = require('grpc-error')

const error = new GRPCError('Boom', 2000, { status_code: 'INVALID_TOKEN' )
console.log(err instanceof Error) // true
console.log(err.message) // 'Boom'
console.log(err.code) // 2000
console.log(err.metadata instanceof grpc.Metadata) // true
console.log(err.metadata.getMap()) // { status_code: 'INVALID_TOKEN' }
```

```js
const GRPCError = require('grpc-error')

const error = new GRPCError('Boom', { status_code: 'INVALID_TOKEN' )
console.log(err instanceof Error) // true
console.log(err.message) // 'Boom'
console.log(err.metadata instanceof grpc.Metadata) // true
console.log(err.metadata.getMap()) // { status_code: 'INVALID_TOKEN' }
```

## License

  Apache-2.0
