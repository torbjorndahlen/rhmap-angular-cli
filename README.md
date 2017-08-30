# rhmap-angular-cli
Follow these steps to build an Angular CLI/TypeScript app with Cordova and import into RHMAP.

## Import an existing Angular2 CLI project
1. Install Angular Core
2. Run ng new <app-name>
3. Copy the app directory from the original project to the new project

## Add $fh to the app
1. Add "fhconfig.json" to the assets list in angular-cli.json
```
"apps": [
    {
      "root": "src",
      "outDir": "dist",
      "assets": [
        "fhconfig.json"
      ],
```
2. Import fh-js-sdk, for example
```
import { CloudOptions } from 'fh-js-sdk';
import { cloud } from 'fh-js-sdk';
```


## Steps
1. Install node 6.11.1, npm 3.10.10, cordova 7.0.1, Android Studio (android level 25)
2. Create a cordova project with `cordova create` within Angular CLI project directory
3. cd to the cordova directory
4. cordova platform add browser
4. cordova run browser
5. remove the cordova/www folder
7. cd to the Angular CLI directory
8. ng build --output-path cordova/www/ --base-href="."
9. cd cordova
10. cordova run browser
 

## Import into RHMAP
1. cd into the cordova directory
2. Remove the cordova platforms
3. zip the contents of the directory. Note that the files/directories need to be at the root level of the zip otherwise the import will fail
4. Create a project in RHMAP using import
5. Upload the zip file and generate a cordova app in RHMAP

## Troubleshooting
1. If images aren't shown, verify that index.html contains base href="." and not base href="/"
2. If the Cordova App cannot connect to the CloudApp verify that you have added 'fhconfig.json' in the list of assets in angular-cli.json
