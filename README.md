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

