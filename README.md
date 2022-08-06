b1:npm create-react-app nameapp
b2:npm i customize-cra react-app-rewired -D
b3:"scripts": {
    "start": "react-scripts-rewired start",
    "build": "react-scripts-rewired build",
    "test": "react-scripts-rewired test",
    "eject": "react-scripts-rewired eject"
  },
 b4: tạo file config-overrides.js cùng cấp package.json => thêm
     module.exports =function override(config, env){
    return config
};
b5: npm install --save-dev babel-plugin-module-resolver
b6: tạo file .babelrc cùng cấp package.json => thêm 
{
    "plugins": [
      ["module-resolver", {
        "alias": {
          "~": "./src"
        }
      }]
    ]
  }
  
  b7: tạo file jsonconfig.json cùng cấp package.js => 
  {
    "compilerOptions": {
      "baseUrl": ".",
      "paths": {
        "~/*": ["src/*"]
      }
    }
  }
  b8: thay đổi file config-overrides.js => const { override, useBabelRc } = require("customize-cra");

  module.exports = override(
    // eslint-disable-next-line react-hooks/rules-of-hooks
    useBabelRc()
  );
  b9: npm ad react-router-dom$6
  b10: tạo global style - cài sass - reset css - default css
  b11: cấu hình route
 
