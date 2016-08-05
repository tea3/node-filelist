# node-filelist

Get a list of the absolute path in the file location. This plugin reading all the files in a folder recursively.

## Installation

``` bash
$ npm install node-filelist --save
```

## Usage

For example. If you want to read the image file.

``` javascript
var fl      = require('node-filelist');
var files   = [ "/path-you-want-to-read" ];
var option  = { "ext" : "jpeg|jpg|png|gif" };

fl.read(files, option , function (results){
    for(var i=0; i<results.length; i++){
      console.log(results[i].path);
      //console.log(results[i].stats.mtime);   	// If you want stats.mtime , option.isStats should set true.
    }
});
```

It will be in the following such a results.

``` bash
/path-you-want-to-read/sample-1.jpg
/path-you-want-to-read/example-dir/sample-2.jpg
/path-you-want-to-read/sample-3.png
/path-you-want-to-read/sample-4.gif
...
```

## Option

| option | description | default |
| :---: | :--- | :--- |
| ext | Extension of the file you want to read. | all file |
| isStats | If you want [stats](https://nodejs.org/api/fs.html#fs_class_fs_stats "Documentation - node.js") in results. | `false` |


## Results

| results | description |
| :---: | :--- |
| path | The path of the file that you have read . |
| stats | The [stats](https://nodejs.org/api/fs.html#fs_class_fs_stats "Documentation - node.js") of the file that you have read . |

## License

MIT