# mongodbcompass_darktheme

Tested with last version of mongodb Compass (1.26.1), no need to unpack asar file

## STEP 1 : download darkreader script

### LINUX/WSL
go in your mongodb compass folder:

```
cd /usr/lib/mongodb-compass/resources/
sudo wget https://cdn.jsdelivr.net/npm/darkreader/darkreader.min.js
```
### WIN

download: https://cdn.jsdelivr.net/npm/darkreader/darkreader.min.js and copy the file in mongodb compass resources folder (default MSI installation):
C:\Program Files\MongoDB Compass\resources

## STEP 2 (WIN/LINUX) : inject in electron app

open mongodb compass (this step need to be executed each time you use mongodb compass), toggle dev tools, in console write:
```
var jq = document.createElement('script');
```
(enter)
```
jq.src = "./../../../darkreader.min.js";
```
(enter)
```
document.getElementsByTagName('head')[0].appendChild(jq);
```
(enter)
```
DarkReader.enable({
    brightness: 100,
    contrast: 90,
    sepia: 10
});
```
(enter, adjust values if necessary)  
don't worry about CSP errors  
mongodb compass electron app don't integrate it as npm package probably due to CSP requirements  
voila ^^  

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate?hosted_button_id=UKRSA8MGPWYWJ)
