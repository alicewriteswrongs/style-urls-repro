# styleUrls reproduction case

This reproduces https://github.com/ionic-team/stencil/issues/5016

We claim to support `styleUrls`, putting multiple stylesheets into a component,
but this doesn't work!

In this repro `my-component` has two stylesheets, one of which sets the
background to `red`. However, if you:

```sh
npm install
npm start
```

You will not see a red background. You can confirm that it's pulling in only
the _first_ stylesheet by either switching the order of the filenames in
`styleUrls` or checking the `style` tag in the shadow root in the inspector.