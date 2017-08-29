# grpc-error

Utility Error class suitable for gRPC error responses

### Related

[grpc-create-error](https://github.com/bojand/grpc-create-error) - A helper function module that this class uses

[grpc status codes](https://grpc.io/grpc/node/grpc.html) - The grpc status codes.

## Usage
```js
const GRPCError = require('grpc-error')
const grpc require('grpc')
const error = new GRPCError('Boom', grpc.status.INVALID_ARGUMENT)
```

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
