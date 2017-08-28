# rhmap-angular-cli
Follow these steps to build an Angular CLI app with Cordova and import into RHMAP.

## Import an existing Angular2 CLI project
1. Install Angular Core
2. Run ng new <app-name>
3. Copy the app directory from the original project to the new project

## Steps
1. Install node 6.11.1, npm 3.10.10, cordova 7.0.1, Android Studio (android level 25)
2. Create a cordova project with `cordova create` within Angular CLI project directory
3. Add a directory called `scripts` under the `cordova` directory
4. Integrate the cordova build process with ng build by placing the script `prepareAngular2App.js` into the `cordova/scripts` directory
5. Add the android platform with `cordova platform add android`
6. Remove the default `cordova/www` directory
7. Build and run locally with `cordova run android` to verify that the app works locally

## Import into RHMAP
1. Remove the `cordova/platforms` directory
2. cd into the cordova directory
3. zip the contents of the directory. Note that the files/directories need to be at the root level of the zip otherwise the import will fail
4. Create a project in RHMAP using import
5. Upload the zip file and generate a cordova app in RHMAP

## Troubleshooting
If images aren't shown, verify that index.html contains base href="." and not base href="/"
