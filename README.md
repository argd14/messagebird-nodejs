MessageBird REST API for node.js
================================

This repository contains the open source node.js lib for MessageBird's REST API.
Documentation can be found at: https://www.messagebird.com/developers/nodejs


Requirements
------------

- [Sign up](https://www.messagebird.com/en/signup) for a free MessageBird account
- Create a new `access_key` in the [developers](https://www.messagebird.com/app/nl/settings/developers/access) section
- MessageBird REST API for node.js requires node.js >= 0.10 or io.js


Installation
------------

`npm install messagebird`


Usage
-----

We have put some self-explanatory examples in the *examples* directory,but here is a quick breakdown on how it works.
Let's go ahead and initialize the library first. Don't forget to replace `<YOUR_ACCESS_KEY>` with your actual access key.

```javascript
var messagebird = require ('messagebird') .client ('<YOUR_ACCESS_KEY>');
```

Nice! Now we can send API requests through node. Let's use getting your balance overview as an example:

```javascript
// Get your balance
messagebird.balance.read (function (err, data) {
  if (err) { return console.log (err); }
  console.log (data);
});

// Result object:
{
  payment: 'prepaid',
  type: 'credits',
  amount: 42.5
}
```

Or in case of an error:

```javascript
{ [Error: api error]
  errors: [
    {
      code: 2,
      description: 'Request not allowed (incorrect access_key)',
      parameter: 'access_key'
    }
  ]
}
```


Documentation
-------------

Complete documentation, instructions, and examples are available at:
[https://www.messagebird.com/developers/nodejs](https://www.messagebird.com/developers/nodejs)


License
-------
The MessageBird REST API for node.js is licensed under [The BSD 2-Clause License](http://opensource.org/licenses/BSD-2-Clause). Copyright (c) 2014, MessageBird
