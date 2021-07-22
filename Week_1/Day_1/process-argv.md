### Using Command Line Args

While using node, you are able to pass arguments through with the js file.  They then come through in an array.  The first element is always the path to the node executable file, the second element is the path of the file that is passed through and the remaining elements are all the arguments that were passed through separated by spaces.  For example: 

Running: 

`node processargv.js Hello World`  

Will pass through the array process.argv with the below elements:

[0] -> /home/vagrant/.nvm/versions/node/v12.18.2/bin/node <br/>
[1] -> /vagrant/w1/d1-focal/processargv.js<br/>
[2] -> "Hello"<br/>
[3] -> "World"

```javascript
'use strict';

for (let j = 0; j < process.argv.length; j++) {
  console.log(j + ' -> ' + (process.argv[j]));
}
```

This for loop will print each of those elements to the screen with their index number as well.

You can skip over the first 2 elements of the array by using slice similar to the below example:

```javascript
'use strict';
let sum = 0;
process.argv.slice(2).forEach(element => sum += Number(element));

console.log(sum);
```