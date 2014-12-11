# Racket buildpack for Cloud Foundry

A simple buildpack that fetches Racket 6.1.1, and builds your project and deploys it.

This expects that you'll have a main.rkt file in your app as the main executable.

## Usage

```bash
cf push racketapp -b https://github.com/robdaemon/racket-buildpack
```