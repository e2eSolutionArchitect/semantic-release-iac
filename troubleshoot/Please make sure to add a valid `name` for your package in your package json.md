Error reference https://github.com/TheSolutionArchitect/tf-aws-template-core-live/actions/runs/12830405273/job/35778516713
Error 

```
at async next (file:///home/runner/work/tf-aws-template-core-live/tf-aws-template-core-live/node_modules/semantic-release/node_modules/p-reduce/index.js:15:44) {
      code: 'ENOPKGNAME',
      details: "The `package.json`'s [name](https://docs.npmjs.com/files/package.json#name) property is required in order to publish a package to the npm registry.\n" +
        '\n' +
        'Please make sure to add a valid `name` for your package in your `package.json`.',
      semanticRelease: true,
      pluginName: '@semantic-release/npm'
    }
```

Solution:

.releaserc file was missing in the repository root. 
Add .releaserc file https://github.com/e2eSolutionArchitect/semantic-release-iac/blob/main/.releaserc
