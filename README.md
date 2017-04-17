Gauge-Nightly-Repository
========================

This contains the nightly meta-data of [gauge plugins and language runners](http://getgauge.io/documentation/user/current/plugins/README.html) which is used during installation and upgrades.

### Steps to add new plugin details :
* Add a file with name {plugin_name}-install.json in the base directory.
* Following snippet shows the json format for the above file.
```
{
    "name": "{plugin_name}",
    "description": "{description}",
    "versions": [
        {
            "version": "{version_number}",
            "gaugeVersionSupport": {
                "minimum": "{minimum gauge version supported}",   //mandatory
                "maximum": "{maximum gauge version supported}"    //optional
            },
            "install": {
                //Command to start the plugin which should be relative to plugin directory
                "windows": [],
                "linux": [],
                "darwin": []
            },
            "DownloadUrls": {
                //Download url for each platform, if the links are not present,
                //gauge assumes the plugin does not support that platform.
                "x86": {
                    "windows": "",  
                    "linux": "",
                    "darwin": ""
                },
                "x64": {
                    "windows": "",
                    "linux": "",
                    "darwin": ""
                }
            }
        }
    ]
}
```
* For reference, have a look at our [plugin](https://github.com/getgauge/gauge-nightly-repository/blob/master/java)
