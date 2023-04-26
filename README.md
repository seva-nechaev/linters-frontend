## Demo project as a example of useful linters

1. Eslint for code best practices
1. Prettier for formatting
1. Cspell for detecting typos
1. Jscpd for duplication detection


## Linters and code analysis tools
- Formatting(prettier)
- Code duplication linter(jscpd)


### Formatting 
```
npm run format
``` 
This runs [Prettier](https://prettier.io), check `package.json` for details
Formatting can be configured in [.prettierrc](.prettierrc) and [.prettierignore](.prettierignore). See [Options](https://prettier.io/docs/en/options.html) for details.  


### Code duplication 
We use npm library js-copy-paste-detector for checking duplication code.
More info about js-copy-paste-detector library [npm jscpd](https://www.npmjs.com/package/jscpd)

#### How to use
Execute `npm install -g jscpd && jscpd`

Duplication check does
1. Print detailed report to the console. Example: 
    ```
    Clone found (markup):
    - src/components/HelloWorld-duplicated.vue [9:1 - 44:2] (35 lines, 225 tokens)
    src/components/HelloWorld.vue [5:1 - 40:2]

    9  │ 5  │ </script>                                                                                 
    10 │ 6  │                                                                                           
    11 │ 7  │ <template>                                                                                
    12 │ 8  │   <div class="greetings">                                                                 
    13 │ 9  │     <h1 class="green">{{ msg }}</h1>    
    ```
1. Generate html report [index.html](reports/html/index.html), but in current jscpd version this report is __broken__ 
1. Generate summary report in `.md` format [jscpd-report.md](reports/jscpd-report.md)

#### Configuration
Configuration file is [.jscpd.json](.jscpd.json)
Not default configuration values: 
- __min-lines__  equals 10(default 5) to ignore small code duplication blocks
- __minTokens__ equals 90(default 50) to ignore small code duplication blocks




