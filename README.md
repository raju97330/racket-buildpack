# Racket buildpack for Cloud Foundry

A simple buildpack that fetches Racket 6.1.1, builds your project and deploys it.

This expects that you'll have a `main.rkt` file in your app as the main executable.

## Usage

```bash
cf push racketapp -b https://github.com/robdaemon/racket-buildpack
```

## How it works

Build your app as you normally would, but ensure there's a file called `main.rkt`
in the root of your app. This is the main entry point.

When the app is pushed to Cloud Foundry, it is compiled with `raco exe` and then
is built into a distribution with `raco distribute` and placed in the `racketapp`
folder.

Your app should use the following command to start it:

```
./racketapp/bin/main
```

This can be modified as necessary (additional command line parameters, environment
variables, etc) but the main executable is always named `main` from this build pack.

## Example

You can find an example app using this build pack at: https://github.com/robdaemon/cf-racket-hello

## License

This is released under the terms of the Apache Public License 2.0.
