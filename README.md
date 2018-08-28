# q-spec: the specification for the quantity level q

## Background
I needed a way to show the level of quantity concisely.

## Definition
The quantity level q of a quantity v is defined as the following.

- -1 if v = 0
- floor(log2(v)) otherwise

## Implemenetation note
In the actual case of the implementation, the function to get q can be implemented using bit shift. 

For example, [q.js](https://github.com/hfu/q/blob/master/q.js) implements the function q(v) as the following:

```javascript
const q = v => {
  for(let i = 0; true; i++) {
    if(v / (2 ** i) < 1) return i - 1
  }
}
```

## See also
- [q](https://github.com/hfu/q): Ruby and JavaScript implementation of quantity level q
- [mbq](https://github.com/hfu/mbq): A tool to get qmatrix from mbtiles
