project('foreach', 'c')

tests = [['test1', 'prog1', 'prog1.c'],
  ['test2', 'prog2', 'prog2.c', 'fallback'],
  ['test3', 'prog3', 'prog3.c', 'urgh']]

assert(tests[0].get(3, 'fallbck') == 'fallbck', 'array #1 fallback did not match')
assert(tests[1].get(3, 'failbk') == 'fallback', 'array #2 value did not match')
assert(tests[2].get(3, 'urgh') == 'urgh', 'array #3 value did not match')

foreach i : tests
  test(i.get(0), executable(i.get(1), i.get(2), install : true))

  # Ensure that changing the tests variable does not
  # affect ongoing iteration in the foreach loop.
  #
  # Being able to do that would make Meson Turing complete and
  # we definitely don't want that.
  tests = ['test4', 'prog4', 'prog4.c']
endforeach
