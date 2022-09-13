# Appendix C: Pointfree Utilities

In this appendix, you'll find pointfree versions of rather classic JavaScript functions
described in the book. All of the following functions are seemingly available in exercises, as
part of the global context. Keep in mind that these implementations may not be the fastest or
the most efficient implementation out there; they *solely serve an educational purpose*.

In order to find functions that are more production-ready, have a peek at
[ramda](https://ramdajs.com/), [lodash](https://lodash.com/), or [folktale](http://folktale.origamitower.com/).

Note that functions refer to the `curry` & `compose` functions defined in [Appendix A](./appendix_a.md)

## add 

```javascript
// add :: Number -> Number -> Number
const add = curry((a, b) => a + b);
```

## append

```javascript
// append :: String -> String -> String
const append = flip(concat);
```

## chain

```javascript
// chain :: Monad m => (a -> m b) -> m a -> m b
const chain = curry((fn, m) => m.chain(fn));
```

## concat

```javascript
// concat :: String -> String -> String
const concat = curry((a, b) => a.concat(b));
```

## eq

```javascript
// eq :: Eq a => a -> a -> Boolean
const eq = curry((a, b) => a === b);
```

## filter

```javascript
// filter :: (a -> Boolean) -> [a] -> [a]
const filter = curry((fn, xs) => xs.filter(fn));
```

## flip

```javascript
// flip :: (a -> b -> c) -> b -> a -> c
const flip = curry((fn, a, b) => fn(b, a));
```

## forEach 

```javascript
// forEach :: (a -> ()) -> [a] -> ()
const forEach = curry((fn, xs) => xs.forEach(fn));
```

## head

```javascript
// head :: [a] -> a
const head = xs => xs[0];
```

## intercalate

```javascript
// intercalate :: String -> [String] -> String
const intercalate = curry((str, xs) => xs.join(str));
```

## join

```javascript
// join :: Monad m => m (m a) -> m a
const join = m => m.join();
```

## last

```javascript
// last :: [a] -> a
const last = xs => xs[xs.length - 1];
```

## map

```javascript
// map :: Functor f => (a -> b) -> f a -> f b
const map = curry((fn, f) => f.map(fn));
```

## match

```javascript
// match :: RegExp -> String -> Boolean
const match = curry((re, str) => re.test(str));
```

## prop 

```javascript
// prop :: String -> Object -> a
const prop = curry((p, obj) => obj[p]);
```

## reduce

```javascript
// reduce :: (b -> a -> b) -> b -> [a] -> b
const reduce = curry((fn, zero, xs) => xs.reduce(fn, zero));
```

## replace

```javascript
// replace :: RegExp -> String -> String -> String
const replace = curry((re, rpl, str) => str.replace(re, rpl));
```

## reverse

```javascript
// reverse :: [a] -> [a]
const reverse = x => (Array.isArray(x) ? x.reverse() : x.split('').reverse().join(''));
```

## safeHead

```javascript
// safeHead :: [a] -> Maybe a
const safeHead = compose(Maybe.of, head);
```

## safeLast

```javascript
// safeLast :: [a] -> Maybe a
const safeLast = compose(Maybe.of, last);
```

## safeProp

```javascript
// safeProp :: String -> Object -> Maybe a
const safeProp = curry((p, obj) => compose(Maybe.of, prop(p))(obj));
```

## sequence

```javascript
// sequence :: (Applicative f, Traversable t) => (a -> f a) -> t (f a) -> f (t a)
const sequence = curry((of, f) => f.sequence(of));
```

## sortBy

```javascript
// sortBy :: Ord b => (a -> b) -> [a] -> [a]
const sortBy = curry((fn, xs) => xs.sort((a, b) => {
  if (fn(a) === fn(b)) {
    return 0;
  }

  return fn(a) > fn(b) ? 1 : -1;
}));
```

## split

```javascript
// split :: String -> String -> [String]
const split = curry((sep, str) => str.split(sep));
```

## take

```javascript
// take :: Number -> [a] -> [a]
const take = curry((n, xs) => xs.slice(0, n));
```

## toLowerCase

```javascript
// toLowerCase :: String -> String
const toLowerCase = s => s.toLowerCase();
```

## toString

```javascript
// toString :: a -> String
const toString = String;
```

## toUpperCase

```javascript
// toUpperCase :: String -> String
const toUpperCase = s => s.toUpperCase();
```

## traverse

```javascript
// traverse :: (Applicative f, Traversable t) => (a -> f a) -> (a -> f b) -> t a -> f (t b)
const traverse = curry((of, fn, f) => f.traverse(of, fn));
```

## unsafePerformIO

```javascript
// unsafePerformIO :: IO a -> a
const unsafePerformIO = io => io.unsafePerformIO();
```
