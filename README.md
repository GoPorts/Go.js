![Easy to write, Fast Performance](https://github.com/user-attachments/assets/1be46de0-f76e-40b4-8e9b-7bf7a10eb161)



[![Download zip](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white "Download Zip")](https://github.com/sebastian-sestaliuc/Go.js/releases/tag/v1) 
<br /> <br />
 [![Download zip](https://img.shields.io/badge/Download-blue)](https://github.com/GoPorts/Go.js/blob/main/README.md#-download) <br /> 
<br />
# What is Go.js? <br />
**Go.js is still in beta, thus it can give you code that dosent work, be aware** <br /> <br />
Go.js is a JavaScript/TypeScript code that converts simple words into GO code <br />
Go.js is still under development <br />
you also must know that your antivirus might get trigget of the js code, if it does download the .txt file insted <br />
more info by scrolling down <br />
<br /><br />
 <hr>
 
 • How to setup <br />
 
‎ ‎  ◦ after you've open Go.js, you can put some words in your coding space (go = ´´). <br />
‎ ‎  ◦ you only need a JavaScript or TypeScript compiler, and the your done! <br />

 • All keywords for Go.js <br />
 
‎ ‎  ◦ start, by typing start it'll create the package and import <br />
‎ ‎  ◦ print , we know what print does <br />
‎ ‎  ◦ input , we also know what input does <br />
‎ ‎  ◦ var, to create a variable you do this ´var hello = "world"´ <br />

 • Why make this? <br />
 
‎ ‎  ◦ since Go is in high demand, its also in high value <br />
‎ ‎  ◦ for people that can code in JavaScript but not Go <br />
‎ ‎  ◦ and if you use AI to convert the code, you might result in bad code <br />

 • Other info <br />
 
‎‎   ◦ Go.js is source free, which means that other people can use it <br />
‎‎   ◦ Go.js is still under development <br />

# • Download
 [![Download zip](https://img.shields.io/badge/Version-v1.0.0-blue)](https://github.com/GoPorts) <br /> 
 
```
  let go = `
   start

`;



let gocode
/*
 * Creating the package and import if it begins with start
 * print = fmt.Println("")
 * input = fmt.Scanln()
 * var name = value 
 * @start
*/
gocode = ""
if (go.includes("start")) {
    gocode+=(`
package main

import "fmt"
       
func main(){
    `);
    if (go.includes("print ")) {
        const textToPrint = go.split("print ")[1].split("\n")[0].trim();
        gocode+=(`    fmt.Println("${textToPrint}")`);
    }
    if (go.includes("var ")) {
        const variableLine = go.split("var ")[1].split("\n")[0].trim();
        const valuetype = prompt(`value type for ${variableLine}`);
        const value = prompt(`value for ${variableLine}`);
        if (valuetype === "bool") {
            gocode+=(`    ${variableLine} := ${value}`);
        } else if (valuetype === "string") {
            gocode+=(`    ${variableLine} := "${value}"`);
        } else if (valuetype === "int" || valuetype === "float64") {
            gocode+=(`    ${variableLine} := ${value}`);
        }
    }
    if (go.includes("input ")) {
        const inputVar = go.split("input ")[1].split("\n")[0].trim();
        gocode+=(`    fmt.Scanln(&${inputVar})`);
    }

    gocode+=(`
}
            `);
}
console.log(gocode)
```
