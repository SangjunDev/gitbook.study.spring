# API

**ResponseBody 문자, 객체 반환**

```
@GetMapping("hello-string")
    @ResponseBody
    public String helloString(@RequestParam("name") String name){
        return "hello" + name;
    }

    @GetMapping("hello-api")
    @ResponseBody
    public Hello helloApi(@RequestParam("name") String name) {
        Hello hello = new Hello();
        hello.setName(name);
        return hello;
    }
    static class Hello {
        private String name;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }
    }
```



![](<../../.gitbook/assets/스크린샷 2022-05-16 오후 9.44.37.png>)

**객체가 오면  Default: Json으로 반환**

****
