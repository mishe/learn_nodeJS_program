> 看了一些node资料，都没有现成的文件目录遍历的代码，我自己尝试着写了下。代码如下

```javascript
var fs=require('fs'),
    path=require('path'),
    dir='./';

function traverse(dir){
    fs.readdir(dir,function(err,files) {
        if (err) {
            console.log(dir,err)
        } else {
            //console.log(files)
            files.forEach(function (file) {
                fs.stat(path.join(dir,file), function (err, state) {
                    if (err) {
                        console.log(err)
                    } else {

                        if(state.isDirectory()){
                            traverse(path.join(dir,file));
                            //traverse(dir+file)
                        }else if(state.isFile()){
                            console.log(path.resolve(path.join(dir,file)))
                        }
                    }
                })
            });
        }
    });
}


traverse(dir)
```
