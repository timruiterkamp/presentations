# Presentation 2

## node and npm presentation

### node

* Javascript
* Efficient Input / output
* fast
* A-sync

### Javascript

* primitieven: data-types, dingen die in variabalen zitten als strings, numbers en boolean
* if / else boven liggend
* JSON (parsen en stringify'en), Math(random, pi etc.), Date

### node includes

* Process

  * cwd() - Prints out directory
  * exit() - Stops the process
  * env() - shows objects that are available, the complete enviroment
  * argv() - add arguments to object, returns an array of elements. Start bij [2].
  * stdin - gets information out other file as input, can do with it what u want
  * stdout - sends/prints information as output
  * stderr - use as error messages or debug information

* require('events')

  * on() - listen to functions or actions / process.on('exit', function);
  * EventEmitter() - listen to events
  * emit() - sends event
  * removeListener() - stops listening / opposite of on()

* Url

  * Info about the url

* Path

  * sep() - seperate path into array foo/bar/baz.split.sep() = [foo, bar, baz]
  * dirname() - gets folder name
  * extname() - get extension name
  * basename() - bestandsnaam
  * relative() - get form one path to another
  * resolve() - makes path absolute

* Buffer

  * zit binare data in

* fs

  * readdir() - Reads what kind of files there are in your directory
  * readFile() - reads file
  * writeFile() - writes file
  * unlink() - removes files and folders
  * rename() - moves file from a place to a place
  * copyFile() - copy the file

* Stream
  * createReadStream() - Create readstream that connects to another file. Reads file linked to result | other side of the netwerk | return results. Connection is divided in chunks
  * pipe() - connect file
  * WriteStream() - send information to file
  * Don't read the full file at once but in chunks

### Callbacks

```javascript
var value;

increment(log);

console.log(value); //=> undefined

function increment(callback) {
  fs.readFile("value.txt", function(err, buf) {
    if (err) throw err;

    value = number(buf);
    value++;

    callback();
  });
}

function log() {
  console.log(value);
}
```

### Node principles

module.exports = sum
var sum = require('./sum')

npm init --yes
