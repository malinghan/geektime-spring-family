#### context-hierarchy-demo 
演示的是ApplicationContext的层次关系。

不同ApplicationContext尽管具有父子层级，也不能共享Bean

#### cache-demo
```
  @RequestMapping(path = "/{id}", method = RequestMethod.GET,
            produces = MediaType.APPLICATION_JSON_UTF8_VALUE)
    @ResponseBody
    public ResponseEntity<Coffee> getById(@PathVariable Long id) {
        Coffee coffee = coffeeService.getCoffee(id);
        return ResponseEntity.ok()
                .cacheControl(CacheControl.maxAge(10, TimeUnit.SECONDS))
                .body(coffee);
    }
```

#### 
