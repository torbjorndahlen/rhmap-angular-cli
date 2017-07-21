# rhmap-angular-cli
Follow these steps to build an Angular CLI app with Cordova and import into RHMAP.

## Steps
0. Install node 6.11.1, npm 3.10.10, cordova 7.0.1, Android Studio (android level 25)
1. Create a cordova project with `cordova create` within Angular CLI project directory
2. Remove the default `cordova/www` directory
3. Add a directory called `scripts` under the `cordova` directory
4. Integrate the cordova build process with ng build by placing the script `prepareAngular2App.js` into the `cordova/scripts` directory
5. Add the android platform with `cordova platform add android`
6. Build and run locally with `cordova run android` to verify that the app works locally

## Import into RHMAP
1. Remove the `cordova/platforms` directory
2. cd into the cordova directory
3. zip the contents of the directory. Note that the files/directories need to be at the root level of the zip otherwise the import will fail
4. Create a project in RHMAP using import
5. Upload the zip file and generate a cordova app in RHMAP
