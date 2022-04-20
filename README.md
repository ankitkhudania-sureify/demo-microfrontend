# Microfrontend Demo with React

## Advantages and limitations

### Advantages

- **Composition** is straightforward: just reference each _microfrontend_ library the way you usually work with third-party packages.
- **Versioning** can be achieved using _web app_ `package.json` and _semVer_.
- **A/B testing**: thanks to the previous point, making two building composing different versions of microfrontends is trivial. At that point, we can publish them and apply A/B testing easily.
    - This implies some compatibility among the different versions you pick, of course.
- **Testability** is somewhat simplified, since each library can be developed and tested independently. Additionally, it is possibile to leverage small _demo_ projects to test them end-to-end as well.

### Limitations

This is a basic demo, and not a complete solution to tackle any situation or requirement.

- **Multiple Frameworks**: so far, it is NOT possibile to mix different frameworks or libraries. The example is done with React, and can be rebuilt with Angular as well, but mixing them is hard.


## Usage

```bash

cd cart
npm install
npm run build
npm link

cd ../catalog
npm install
npm run build
npm link

cd ../web
npm install
npm link microfrontend-cart microfrontend-catalog
npm start
```