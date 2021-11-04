# Generate RESOURCES.md Action

This action reads data from the Developer DAO Airtable and puts its content into README.md.

## Authors

- [@gjsyme](https://github.com/gjsyme)
- [@codingwithmanny](https://github.com/codingwithmanny)

## Local Requirements

- NVM or Node `v16.13.0`

## Local Setup

```bash
yarn install;
```

## Local Tests

```bash
yarn test;
```

## How To Run Locally

**NOTE:** `DO NOT` run this from within the `actions/generate-resources` folder, it will overwrite this `README.md`.

```bash
# make sure you're in the repo root
node .github/actions/generate-resources/main.js --run;

# clean up
node .github/actions/generate-resources/node_modules/.bin/prettier README.md --write;
```

## Inputs

None

## Outputs

None

## Example usage 

```yaml
uses: actions/hello-world-javascript-action@v1.1
with:
  who-to-greet: 'Mona the Octocat'
```

Full example:

```yaml
jobs:
  refresh:
    name: Scheduling
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Enable node
        uses: actions/setup-node@v2
        with:
          node-version: 16.x
      
      - name: Install dependencies
        run: cd ./.github/actions/generate-resources && yarn install --frozen-lockfile

      # Example use
      - name: Run action
        uses: ./.github/actions/generate-resources
```