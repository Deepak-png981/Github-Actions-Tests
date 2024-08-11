- initialize the `actions.yml`
- Add the name , description of the actions
- Then you have to mention what kind of the action it is , their are three types of actions right now javascript actions , docker images actions and the last one is `composite actions`.
Like this `action.yml`: 
```yml
name: Deepak Understanding Github Actions
description: Understanding Github Actions
runs:
  using: node16
  main: src/index.js
```

Then to create a workflow create `.github/workflows/test.yml` file to write the workflow :
```yml 
name: Test
on:
  push

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Use Node.js 16
        uses: actions/setup-node@v2
        with:
          node-version: 16
      - uses: ./ # Uses an action in the root directory
```