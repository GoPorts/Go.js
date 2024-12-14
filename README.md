![Easy to write, Fast Performance](https://github.com/user-attachments/assets/1be46de0-f76e-40b4-8e9b-7bf7a10eb161)

[![Download zip](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white "Download Zip")](https://github.com/sebastian-sestaliuc/Go.js/releases/tag/v1) 
<br /> <br />
 [![Download zip](https://img.shields.io/badge/Code-green)](https://github.com/GoPorts/Go.js/blob/main/README.md#-code-copy-paste) <br /> 
<br />
# What is Go.js? <br />
**Go.js is still in beta, thus it can give you code that dosent work, be aware.** <br /> <br />
Go.js is a JavaScript/TypeScript code that converts simple words into GO code. <br />
Go.js is still under development. <br />
you also must know that your antivirus might get trigget of the js code, if it does download the .txt file insted, <br />
more info by scrolling down <br /> <br />

> [!WARNING]
> Use it in DevTools since its code has prompts in it which your code editor might not support, <br />
> thus your code editor will give you an error! <br />

<br />
 <hr>
 
 • How to setup <br />
 
‎ ‎  ◦ after you've open Go.js, you can put some words in your coding space (go = ´´). <br />
‎ ‎  ◦ you only need a JavaScript or TypeScript compiler, and the your done! <br />

 • All keywords for Go.js <br />
 
‎ ‎  ◦ start, by typing start it'll create the package and import. <br />
‎ ‎  ◦ print , we know what print does <br />
‎ ‎  ◦ input , we also know what input does <br />
‎ ‎  ◦ v!, to create a variable you do this ´v! hello = "world"´.<br />
‎ ‎  ◦ if, if statement is more simpler with Go.js, this is how, if var is val then{}.<br />

 • Why make this? <br />
 
‎ ‎  ◦ since Go is in high demand, its also in high value. <br />
‎ ‎  ◦ for people that can code in JavaScript but not Go. <br />
‎ ‎  ◦ and if you use AI to convert the code, you might result in bad code. <br />

 • Other info <br />
 
‎‎   ◦ Go.js is source free, which means that other people can use it. <br />
‎‎   ◦ Go.js is still under development. <br />
‎‎   ◦ Go.js can only be used on DevTools (Inspect > Console), since its code also has prompts.

# • Code, copy paste
 [![Download zip](https://img.shields.io/badge/Version-v1.1.1-blue)](https://github.com/GoPorts) <br /> 
 
```js
let go = `
start
print Hello, World!
v! name = input
if name is John then
    v! age = input
    if age is 30 then
        fmt.Println("John is 30!")
    else {
        fmt.Println("John is not 30!")
    }
else {
    fmt.Println("Not John!")
}`;
`;
// example up here! /\
let gocode;

gocode = "";
if (go.includes("start")) {
    gocode += `package main\n\nimport "fmt"\n\nfunc main(){\n`;

    if (go.includes("print ")) {
        const textToPrint = go.split("print ")[1].split("\n")[0].trim();
        gocode += `    fmt.Println("${textToPrint}")\n`;
    }

    if (go.includes("v! ")) {
        const variableLine = go.split("v! ")[1].split("\n")[0].trim();
        const [varName, operation] = variableLine.split("=").map(s => s.trim());
        if (operation === "input") {
            gocode += `    var ${varName} string\n    fmt.Scanln(&${varName})\n`;
        }
    }

    if (go.includes("if ")) {
        const conditionLine = go.split("if ")[1].split("then")[0].trim();
        const [variable, comparison] = conditionLine.split("is").map(s => s.trim());
        gocode += `    if ${variable} == "${comparison}" {\n`;

        const thenContent = go.split("then")[1].split("else")[0].trim();
        if (thenContent) {
            // Handle variables and inputs inside 'then'
            if (thenContent.includes("v! ")) {
                const variableLine = thenContent.split("v! ")[1].split("\n")[0].trim();
                const [varName, operation] = variableLine.split("=").map(s => s.trim());
                if (operation === "input") {
                    gocode += `        var ${varName} string\n        fmt.Scanln(&${varName})\n`;
                }
            }
            // Add the actual statements inside 'then'
            gocode += `        ${thenContent}\n`;
        }

        const elseContent = go.split("else {")[1].split("}")[0].trim();
        if (elseContent) {
            gocode += `    } else {\n`;

            // Handle variables and inputs inside 'else'
            if (elseContent.includes("v! ")) {
                const variableLine = elseContent.split("v! ")[1].split("\n")[0].trim();
                const [varName, operation] = variableLine.split("=").map(s => s.trim());
                if (operation === "input") {
                    gocode += `        var ${varName} string\n        fmt.Scanln(&${varName})\n`;
                }
            }
            gocode += `        ${elseContent}\n    }\n`;
        } else {
            gocode += `    }\n`;
        }
    }

    gocode += `}\n`;
}

console.log(gocode);
```
