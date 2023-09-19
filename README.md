# Webpack 프로젝트 생성 Tutorial


1. 프로젝트 생성
```
npm init - y
```


2. webpack 다운로드
```
npm install webpack webpack-cli webpack-dev-server html-webpack-plugin --save-dev
```


3. 파일 생성
```
/src/index.js
/index.html
/webpack.config.js
```


4. 웹팩 설정 파일
```
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
module.exports = {
        // 개발모드, 빌드(운영)모드 설정
        mode: 'none',
        // 처음 진입하는 js 파일 설정
        entry: './src/index.js',
        // 빌드 완료시 하나로 묶을 js 파일 설정
        output: {
            filename: 'main.js',
            path: path.resolve(__dirname, 'dist'),
        },
        // 플러그인 설정
        plugins: [
            new HtmlWebpackPlugin({
                template: 'index.html'
            })
        ],
        // 개발서버 설정 (webpack-dev-server 설정)
        devServer: {
            port: 9000
        }
}
```


5. 웹팩 프로젝트 실행 테스트
```
npx webpack --config webpack.config.js
```


6. NPM Scripts 설정
package.json 수정
```
"scripts": {
  "dev": "webpack serve",
  "build": "webpack"
}
```


7. NPM Scripts 실행 테스트
```
npm run build
npm run dev
```

