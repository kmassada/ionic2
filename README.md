# Bootsrap 

## using nvm to install node's compatible version
```
nvm install v5.11.1
nvm use default  v5.11.1
nvm alias default  v5.11.1
```

## installing ionic's prereqs 
```
npm install -g ionic@beta
npm install -g ios-sim
npm install -g cordova
```

## creating ionic project
```
ionic start nuIonic2 --v2
```

## android
```
ionic platform add android
```

### Android studio
install android studio 

https://developer.android.com/studio/index.html 

make sure your PATH has the location of your android tools example

```
export PATH="$PATH:$HOME/Library/Android/sdk/tools"
```

run

```
ionic run android
```

### Genymotion
install genymotion.app 

https://docs.genymotion.com/Content/01_Get_Started/Installation.htm


install plugin for android studio

https://docs.genymotion.com/pdf/PDF_Plugin_for_Android_Studio/Plugin-for-Android-Studio-1.0.7-Guide.pdf

create a VM and make sure it runs

https://docs.genymotion.com/Content/02_Application/Starting_Genymotion.htm

emulate

```
ionic emulate android
```

## ios
```
ionic platform add ios
ionic emulate ios
```
# TYPESCRIPT

## ts builds

```
npm install tsd -g

tsd init
tsd install ionic cordova --save

npm install --save-dev gulp-tsd
npm install --save-dev gulp-typescript
```

- tsd allows us to compile tsd resources, since they are in .gitignore, this will come handing in production.
- ts allows us to compile typscript to destination using same `tsconfig.json`, we already are able to do this via texteditor, but again, this will help at deployment.

gulpfile.js
```
var tsd = require('gulp-tsd');
var typescript = require('gulp-typescript');

gulp.task('tsd', function(callback) {
  tsd({
    command: 'reinstall',
    config: './tsd.json',
  }, callback);
});

gulp.task('ts', ['tsd'], function() {
  var typescriptProject = typescript.createProject('./tsconfig.json');
  typescriptProject.src([paths.src])
   .pipe(typescript(typescriptProject))
   .js.pipe(gulp.dest('www/build/'));
});
```

tsconfig.json
```
{
    "compilerOptions": {
        "target": "es5",
        "module": "commonjs",
        "moduleResolution": "node",
        "sourceMap": true,
        "outDir": "./www/build/",
        "rootDir": "./src",
        "emitDecoratorMetadata": true,
        "experimentalDecorators": true,
        "removeComments": false,
        "noImplicitAny": false,
        "noResolve": true
    },
    "exclude": ["node_modules", "platforms", "www/build/lib"]
}
```

## bower
```
npm install bower -g
bower init
```

.bowerrc
```
{
  "directory": "www/lib"
}
```