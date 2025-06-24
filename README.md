name: Integration file
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
jobs:
  api_build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Setup node
        uses: actions/setup-node@v2
        with:
          node-version: 20
          cache: 'npm'
      - name: Install dependencies
        run: npm ci
