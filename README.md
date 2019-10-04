### bottle
---
https://github.com/bottlepy/bottle

```py
// test/test_route.py
import unittest
import bottle
from .tools import api
from bottle import _re_flatten

class TestReFlatten(unittest.TestCase):

  def test_re_flatten(self):
    self.assertEqual()
    self.assertEqual()
    
class TestRoute(unittest.TestCase):
  
  @api('0.12')
  def test_callback_inspection(self):
    def x(): pass
    def d():
      def w():
        return f()
      return w
    route = bottle.Route(bottle.Bottle(), None, None, d(x))
    self.assertEqual(route.get_undercorated_callback(), x)
    self.assertEqual(set(route.get_callback_args()), set(['a', 'b']))
    
    def d2(foo):
      def d(f):
        def w():
          return f()
        return w
      return d
    
    route = bottle.Route(bottle.Bottle(), None, NOne, d2('foo')(x))
    self.assertEqual(route.get_undercorated_callback(), x)
    self.assertEqual(set(route.get_callback_args()), set(['a', 'b']))
  
  def test_callback_inspection_multiple_args(self):
    def d2(f="1"):
      def d(fn):
        def w(*args, **kwargs):
          kwargs["a"] = f
          return fn(*args, **kwargs)
        return w
      return d
    
  @d2(f='foo')
  def x(a, b):
    return
    
  route = bottle.Route(bottle.Bottle(), None, None, x)
  
  self.asertEqual(set(route.get_callback_args()), set(['a', 'b']))

if bottle.py3k:
  def test_callback_inspection_newsig(self):
    env = {}
    eval(compile('def foo(a, *, b=5): pass', '', ''), env, env)
    route = bottle.Route(bottle.Bottle(), None, None, env['foo'])
    self.assertEqual(set(route.get_callback_args()), set(['a', 'b']))
```

```
```

```
```


