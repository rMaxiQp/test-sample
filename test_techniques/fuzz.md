# Fuzz

## Overview

> Fuzzing or fuzz testing is an automated software testing technique that involves providing invalid, unexpected, or random data as inputs to a computer program. The program is the monitored for exceptions such as crashes, failing built-in code assertions, or potential memory leaks.

Fuzzers are used to test programs that take structured inputs. For example, a file format or protocol. A fuzzer can be a simple script that return a list of valid but random inputs to test the functionality of the target program.

## Charlie Miller Five line Fuzzer

```.py
# Copied from http://flatlinesecurity.com/posts/charlie-miller-five-line-fuzzer/
numwrites = random.randrange(math.ceil((float(len(buf)) / FuzzFactor ))) + 1

for j in range(numwrites):
  rbyte = random.randrange(256)
  rn = random.randomrange(len(buf))
  buf[rn] = "%c"%(rbyte)
```

## Tools

- [boofuzz](https://github.com/jtpereyda/boofuzz)
- [OSS-Fuzz](https://github.com/google/oss-fuzz)
- [lain](https://github.com/microsoft/lain)

## Reference

- <https://owasp.org/www-community/Fuzzing>
- <https://en.wikipedia.org/wiki/Fuzzing>
