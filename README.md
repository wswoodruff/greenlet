<p align="center">
  <img src="https://i.imgur.com/iiCFjjf.png" width="144" height="150">
</p>
<h1 align="center">Greenlet</h1>

> Move an async function into its own thread.
>
> A simplified single-function version of [workerize](https://github.com/developit/workerize).

The name is somewhat of a poor choice, but it was [available on npm](https://npm.im/greenlet).

## Installation & Usage

```sh
npm i -S greenlet
```

Accepts an async function with, produces a copy of it that runs within a Web Worker.

```
greenlet(Function) -> Function
```


## Example

```js
import greenlet from 'greenlet'

let get = greenlet(async url => {
	let res = await fetch(url)
	return await res.json()
})

console.log(await get('/foo'))
```


## License

[MIT](https://oss.ninja/mit/developit)