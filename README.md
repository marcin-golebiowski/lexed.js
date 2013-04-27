## Lexed

A trivial lexer for Javascript.

```javascript
var rules = {
	'<\/[^>]+>': 'close_tag',
	'<[^>]+>': function(match) { return {type: 'open_tag', text: match} },
	'[^<>]+': function(match) { return match; }
};
var l = new Lexed('<div class="intro"><b>Hello!</b></div>', rules);

var token;
while ((token = l.lex()) != Lexed.EOF) {
	console.log(token);
}
```

Take a look at the [tests](https://github.com/tantaman/lexed.js/blob/master/src/test) for more usage examples.