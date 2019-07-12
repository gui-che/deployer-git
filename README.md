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
const components_public_dir = `${base_dir}/dist/`;

const params = {
  base_dir,
  type: "git",
  branch: "master",
  _: []
};

const docParams = {
  ...params,
  public_dir,
  deploy_dir: ".doc",
  repository: { coding: "git@10.59.99.33:/home/git/doc.git" }
};

const componentsParams = {
  ...params,
  public_dir: components_public_dir,
  deploy_dir: ".components",
  repository: { coding: "git@10.59.99.33:/home/git/components.git" }
};

```bash
node index.js
```
# 1.0.4

修复不自动提交的bug
