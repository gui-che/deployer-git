主工程下安装

```bash
yarn add -D gc-deployer-git
npm install gc-deployer-git --save-dev
```

```javascript
// index.js

const deploy = require("gc-deployer-git");
const base_dir = process.cwd();
const public_dir = `${base_dir}/_site/`;

const params = {
  base_dir,
  public_dir,
  type: "git",
  branch: "master"
};

const docParams = {
  ...params,
  deploy_dir: ".doc",
  repository: { coding: "git@10.59.99.33:/home/git/doc.git" }
};

const componentsParams = {
  ...params,
  deploy_dir: ".components",
  repository: { coding: "git@10.59.99.33:/home/git/components.git" }
};

deploy(docParams);
deploy(componentsParams);
```

```bash
node index.js
```
