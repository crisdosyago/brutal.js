# brutal.js

A crazy-small framework for building brutal/brutalist web applications

## small

110 source lines of code. 2 functions: `R` and `render`

## "React like"

This is React/JSX:

```JSX
  function ButtonWidget(props) {
    return (
      <button onClick={() => showModal(props.name)}>
        Show {props.name} Modal
      </button>
    );
  }
```

This is R/brutal.js:

```JavaScript
function ButtonWidget({name}) {
  return R`
    <button click=${() => showModal(name)}>
      Show ${name} Modal
    </button>
  `;
}
```

Basic usage:

```JavaScript
  render(App(), document.getElementById('root'));
```

### Differences to notice

- Event listeners are named by event names directly. No `on-` prefix. So use `click` not `onlclick`
- There is never any need to quote an attribute, brutal does it for you, so 
  `title=${title}` never `title="${title}"`
- every bit of HTML is tagged with an R and written with backticks. Technically, this is an ES6 template literal and template tag function.
- Every replaced value is enclosed in `${...}` instead of `{...}`

## Why brutalist?

To me, brutalist means as close to the basic raw HTML/ JavaScript as possible. 
There's more to do on the roadmap, but for many projects, these simple functions are enough. 
For example, take a look at [a working TodoMVC example](https://dosyago-coder-0.github.io/rvanillatodo/) made with brutal.js.
Everything in brutal is "as close to the metal" ( the JS / HTML ) as possible. This is ensured by their being minimal JS code,
minimal opinionation (everything is just HTML elements and event handlers), leaving you free to structure things however you like. 

## roadmap

- Server side rendering / client-server symmetry
- Encourage / macro-ise targeted forms and named iframes ( sooo brutal )
- Encourage / bundle brutalist CSS sheets

## conclusion

If you know HTML and JS, you know brutal.js. Give it a spin, open an issue, make a PR, and let me know how you're using it, and where you think it should go.

## projects using brutal.js

- [TodoMVC in brutal.js](https://crisdosyago.github.io/rvanillatodo-1/)
