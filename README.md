# Sort Without Articles

A page built to practice sorting arrays. Built for Wes Bos' [JavaScript 30](https://javascript30.com/) course.

[![Screenshot of the Sort Without Articles page](https://res.cloudinary.com/gerhynes/image/upload/v1516657054/Screenshot-2018-1-22_Sort_Without_Articles_oysjib.jpg)](https://gk-hynes.github.io/sort-without-articles/)

## Notes

Create a variable, `sortedBands`, and call `sort` on it.

`Sort` takes a function with parameters, `a` and `b`, the first and second element passed to it. It moves the bigger one, or the one that comes first alphabetically, to the top.

Inside it, use an if statment to check if `a > b`. This will alphabetize them.

This will alphabetize the array but will take articles into account.

So, make a new function, `strip`, and pass it bandName.

Return `bandName` but run `replace` on it. You can use a regular expression to replace a, an, and the in one go. Call `trim` on the end of it to remove unnecessary spaces.

```js
function strip(bandName) {
  return bandName.replace(/^(a |the |an )/i, "").trim();
}
```

Back inside the sort function, you can use a ternary operator, calling strip on a and b.

```js
const sortedBands = bands.sort((a, b) => (strip(a) > strip(b) ? 1 : -1));
```

### Displaying the bands

Now you can select the ul `bands` and set their innerHTML.

Take `sortedBands` and loop over them using `map`, return each band inside an li, and `join` them.

```js
document.querySelector("#bands").innerHTML = sortedBands
  .map(band => `<li>${band}</li>`)
  .join("");
```

When you try to set something to innerHTML that is not a string, such as an array, `toString` is called on it and by default a comma is put between each element.

`join` joins the elements into one big string.
