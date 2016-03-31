## Hashie

Hashie is a small library that implements a hash data structure.

### Installartion
```console
npm i hashie
```

### Usage

```javascript
var Hashie = require('./hashie');

//create a new Hashie object with the desired key.
var myHash = new Hashie(10);

myHash.add(10);
myHash.add(43);
myHash.add(20);
myHash.print();
myHash.erase(10);

```

### What it does

For every element you want to insert (e.g. 543) a new key is generated with a custom modulo (on creation). So the key for ```var myHash = new Hashie(10)``` would be ```yourNumber % 10```. Hashie will push in the position 3 (from 543) and insert the number 543 there.


### API functions
The following methods exist for Hashie (more coming):

```javascript
//Adds element to data structure
myHash.add(number);

//Erases certain element
myHash.erase(number);

//Finds a certain element (boolean)
myHash.find(number);

//Returns the amount of elements in the hash
myHash.getCount();

//Resets the hash
myHash.dump();
```

### Colissions

Since it's a vector, colissions are handled with a simple push method. so the key 3 can have multiple values (543, 643, 943, 743, etc).

### Optimization

Hash is designed for large amounts of data that avoid many colissions (e.g. 01192543 with a key of % 100 to be 43). For a set of 150_000 ids, there'd only be around 150 colissions (which is good).