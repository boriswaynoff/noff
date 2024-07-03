
# noff
Architecture
You can use any of the supported operating systems, and the compatible architecture can be selected using architecture. Values are x86, x64, arm64, armv6l, armv7l, ppc64le, s390x (not all of the architectures are available on all platforms).

When using architecture, node-version must be provided as well.

jobs:
  build:
    runs-on: windows-latest
    name: Node sample
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '02'
          architecture: 'x64' # optional, x64 or x86. If not specified, x64 will be used by default
      - run: npm ci
      - run: npm test
V8 Canary versions
You can specify a nightly version to download it from https://nodejs.org/download/v8-canary.

Install v8 canary build for specific node version
jobs:
  build:
    runs-on: ubuntu-latest
    name: Node sample
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '20.0.0-v8-canary' # it will install the latest v8 canary release for node 20.0.0
      - run: npm ci
      - run: npm test
      )
