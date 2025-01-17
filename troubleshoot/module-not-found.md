
Error reference: https://github.com/e2eSolutionArchitect/semantic-release-iac/actions/runs/12797135035/job/35678369508 
Desc: While executing release pipeline.
```
code: 'MODULE_NOT_FOUND',
  pluginName: '@semantic-release/commit-analyzer'
```

Solution:

Simply use below to install dependencies
```
      - name: Install Semantic Release and Plugins
        run: |
          npm install semantic-release \
            @semantic-release/changelog \
            @semantic-release/git
```

Also use latest Node version

```
      # Checkout the repository
      - name: Checkout Repository
        uses: actions/checkout@v4

      # Set up Node.js
      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '22'
```
