# Vue 3 + TypeScript + Vite + Vue-I18n@8.x.x

## Steps to reproduce
- Clone repo and install dependencies using `npm`;
- Run `npm i vuetify` in terminal;

## Expected behavior
- Vuetify should be installed without any issues;

## Actual behavior
- Vuetify installation fails with the following error:
```
npm ERR! code ERESOLVE
npm ERR! ERESOLVE could not resolve
npm ERR! 
npm ERR! While resolving: vuetify@3.5.17
npm ERR! Found: vue-i18n@8.25.1
npm ERR! node_modules/vue-i18n
npm ERR!   vue-i18n@"^8.25.1" from the root project
npm ERR! 
npm ERR! Could not resolve dependency:
npm ERR! peerOptional vue-i18n@"^9.0.0" from vuetify@3.5.17
npm ERR! node_modules/vuetify
npm ERR!   vuetify@"*" from the root project
npm ERR! 
npm ERR! Conflicting peer dependency: vue-i18n@9.13.1
npm ERR! node_modules/vue-i18n
npm ERR!   peerOptional vue-i18n@"^9.0.0" from vuetify@3.5.17
npm ERR!   node_modules/vuetify
npm ERR!     vuetify@"*" from the root project
npm ERR! 
npm ERR! Fix the upstream dependency conflict, or retry
npm ERR! this command with --force or --legacy-peer-deps
npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
npm ERR!
...
```

## Comments:
- This issue is caused by the fact that `vuetify` has a peer dependency on `vue-i18n@^9.0.0`, while the root project has a dependency on `vue-i18n@^8.25.1`. This causes a conflict between the two versions of `vue-i18n` and the installation fails.
- Using `--force` or `--legacy-peer-deps` flags is not a good solution, as it may lead to potential issues in the future AND/OR may not be an option for all dev/prod servers.