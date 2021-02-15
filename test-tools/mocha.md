# mocha
javascript 테스트 툴

## example
```
it('double done', function(done) {
  // Calling `done()` twice is an error
  setImmediate(done);
  setImmediate(done);
});
```
