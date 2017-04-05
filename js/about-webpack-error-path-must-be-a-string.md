## About Webpack Error - TypeError: Path must be a string.

```
Module build failed: TypeError: Path must be a string. Received undefined
    at assertPath (path.js:7:11)
    at Object.dirname (path.js:1324:5)
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:374:36
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:396:22
    at Array.map (native)
    at OptionManager.resolvePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:385:20)
    at OptionManager.mergePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:369:10)
    at OptionManager.mergeOptions (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:328:14)
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:370:14
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:390:24
    at Array.map (native)
    at OptionManager.resolvePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:385:20)
    at OptionManager.mergePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:369:10)
    at OptionManager.mergeOptions (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:328:14)
    at OptionManager.init (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:481:10)
    at File.initOptions (/react-app/node_modules/babel-core/lib/transformation/file/index.js:211:75)
    at new File (/react-app/node_modules/babel-core/lib/transformation/file/index.js:129:22)
    at Pipeline.transform (/react-app/node_modules/babel-core/lib/transformation/pipeline.js:48:16)
    at transpile (/react-app/node_modules/babel-loader/index.js:14:22)
    at Object.module.exports (/react-app/node_modules/babel-loader/index.js:88:12)
```


First you can remove and reinstall your `node_modules` folder.

if still not working you can try update your `babel-core` to version `6.10.4`.

[Ref](https://github.com/webpack/webpack/issues/2463)

- - -

## 關於 Webpack 錯誤 TypeError: Path must be a string.

```
Module build failed: TypeError: Path must be a string. Received undefined
    at assertPath (path.js:7:11)
    at Object.dirname (path.js:1324:5)
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:374:36
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:396:22
    at Array.map (native)
    at OptionManager.resolvePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:385:20)
    at OptionManager.mergePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:369:10)
    at OptionManager.mergeOptions (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:328:14)
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:370:14
    at /react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:390:24
    at Array.map (native)
    at OptionManager.resolvePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:385:20)
    at OptionManager.mergePresets (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:369:10)
    at OptionManager.mergeOptions (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:328:14)
    at OptionManager.init (/react-app/node_modules/babel-core/lib/transformation/file/options/option-manager.js:481:10)
    at File.initOptions (/react-app/node_modules/babel-core/lib/transformation/file/index.js:211:75)
    at new File (/react-app/node_modules/babel-core/lib/transformation/file/index.js:129:22)
    at Pipeline.transform (/react-app/node_modules/babel-core/lib/transformation/pipeline.js:48:16)
    at transpile (/react-app/node_modules/babel-loader/index.js:14:22)
    at Object.module.exports (/react-app/node_modules/babel-loader/index.js:88:12)
```

首先你可以先把 `node_modules` 刪除掉重新安裝。

還是無法的話，將你的 `babel-core` 升到 `6.10.4` 理應當可以解決。

[相關討論](https://github.com/webpack/webpack/issues/2463) 