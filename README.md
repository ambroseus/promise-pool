<div align="center">
  <a href="https://superchargejs.com">
    <img width="471" style="max-width:100%;" src="https://superchargejs.com/images/supercharge-text.svg" />
  </a>
  <br/>
  <br/>
  <p>
    <h3>Promise Pool</h3>
  </p>
  <p>
    Map-like, concurrent promise processing for Node.js.
  </p>
  <br/>
  <p>
    <a href="#installation"><strong>Installation</strong></a> ·
    <a href="#docs"><strong>Docs</strong></a> ·
    <a href="#usage"><strong>Usage</strong></a>
  </p>
  <br/>
  <br/>
  <p>
    <a href="https://www.npmjs.com/package/@supercharge/promise-pool"><img src="https://img.shields.io/npm/v/@supercharge/promise-pool.svg" alt="Latest Version"></a>
    <a href="https://www.npmjs.com/package/@supercharge/promise-pool"><img src="https://img.shields.io/npm/dm/@supercharge/promise-pool.svg" alt="Monthly downloads"></a>
  </p>
  <p>
    <em>Follow <a href="http://twitter.com/marcuspoehls">@marcuspoehls</a> and <a href="http://twitter.com/superchargejs">@superchargejs</a> for updates!</em>
  </p>
</div>

---

## Installation

```
npm i @supercharge/promise-pool
```


## Docs
Find all the [details and available methods in the extensive Supercharge docs](https://superchargejs.com/docs/promise-pool).


## Usage
Using the promise pool is pretty straightforward. The package exposes a class and you can create a promise pool instance using the fluent interface.

Here’s an example using a concurrency of 2:

```js
const PromisePool = require('@supercharge/promise-pool')

const users = [
  { name: 'Marcus' },
  { name: 'Norman' },
  { name: 'Christian' }
]

const { results, errors } = await PromisePool
  .withConcurrency(2)
  .for(users)
  .process(async data => {
    const user = await User.createIfNotExisting(data)

    return user
  })
```

The promise pool uses a default concurrency of 10:

```js
await PromisePool
  .for(users)
  .process(async data => {
    // processes 10 items in parallel by default
  })
```


## Contributing

1.  Create a fork
2.  Create your feature branch: `git checkout -b my-feature`
3.  Commit your changes: `git commit -am 'Add some feature'`
4.  Push to the branch: `git push origin my-new-feature`
5.  Submit a pull request 🚀


## License
MIT © [Supercharge](https://superchargejs.com)

---

> [superchargejs.com](https://superchargejs.com) &nbsp;&middot;&nbsp;
> GitHub [@superchargejs](https://github.com/superchargejs/) &nbsp;&middot;&nbsp;
> Twitter [@superchargejs](https://twitter.com/superchargejs)
