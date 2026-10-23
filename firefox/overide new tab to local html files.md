use local .html file with the .css or/and .js file that were used for the page

### create the configuration file 
- make a file named: autoconfig.js
in the file:
```
// First line must be a comment
pref("general.config.filename", "firefox.cfg");
pref("general.config.obscure_value", 0);
pref("general.config.sandbox_enabled", false);
```
- make a file named: firefox.cfg
in the file
```
// First line must be a comment
try {
  const ff = {};
  ChromeUtils.defineESModuleGetters(ff, {AboutNewTab: "resource:///modules/AboutNewTab.sys.mjs"});
  ff.AboutNewTab.newTabURL = 'file:///C:/YOUR/PATH/TO/index.html'; 
} catch (e) {
  ChromeUtils.reportError(e);
}
```
> change `file:///C:/YOUR/PATH/TO/index.html` to the actual path

### move the file

| OS      | move firefox.cfg to:                          | move autoconfig.js to:                                      |
| ------- | --------------------------------------------- | ----------------------------------------------------------- |
| Windows | C:\Program Files\Mozilla Firefox\             | C:\Program Files\Mozilla Firefox\defaults\pref\             |
| MacOS   | /Applications/Firefox.app/Contents/Resources/ | /Applications/Firefox.app/Contents/Resources/defaults/pref/ |
| Linux   | /usr/lib/firefox/                             | /usr/lib/firefox/defaults/pref/                             |
- then restart firefox completely for the change to take effect

---
#firefox