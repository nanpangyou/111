---
title: 代码片段-js
categories:
  - Note
  - code
tags:
  - blog
  - code
date: 2019-09-07 16:23:58
---

- curry 函数（可以将函数柯里化的函数）
  当传入的参数个数没有到达 func 函数要求的参数个数的时候一直返回柯里化函数。 只有参数满足 func 函数的个数的时候才通过 apply 执行 func 函数

  ```
    /*
      function curry(???){
          ???
          return ???
      }
      var abc = function(a, b, c) {
        return [a, b, c];
      };
    */

    function curry(fn,thisArg){
        if ( !Array.isArray(thisArg) ) {
                  thisArg = [];
        }
        return function(){
              let args = Array.prototype.slice.call(arguments);
              if ( (args.length+thisArg.length) < fn.length ) {
                  return curry(fn , thisArg.concat(args));
              }
              return fn.apply(this , thisArg.concat(args));
          };
    }

    var abc = function(a, b, c) {
      return [a, b, c];
    };

    var curried = curry(abc);

    curried(1)(2)(3);
    curried(1, 2)(3);
    curried(1, 2, 3);
  ```

  **[参考博客](https://yi-love.github.io/articles/js-func-curry)**
