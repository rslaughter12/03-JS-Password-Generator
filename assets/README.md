Overview:
This project has a goal of creating a random password generator. 
The JS file has declared variables in array form that allow for that data to be recalled randomly through the functions throughtout the sheet. 

When the user opens the website they will be presented with a box and a big red button that says "generate password".
When the button is clicked the user is prompted to decide how many characters that they would like in their password, then a series of questions about what is included in the password (lowercase, uppercase, special, and numbers).

When the user has completed answering all of the questions, then the program will output a random password that meets all of the requests of the user. 

Within the code, the user will be prompted to try again if the system is presented with an unidentified request such as less or more than the character list.


Code information: 
function getPrompts() {
    choiceArr = [];
    characterLength = parseInt(prompt("How many characters do you want your password to contain? (8-128 characters)")) 

    if(isNaN(characterLength) || characterLength < 8 || characterLength > 128) {
        alert("Character length has to be a number, 8 -128 digits. Please try again.");
        return false;
    }
    if (confirm("Would you like lowercase letters in your password?")) {
        choiceArr = choiceArr.concat(lowerCaseArr);
    }
    if (confirm("Would you like uppercase letters in your password?")) {
        choiceArr = choiceArr.concat(upperCaseArr);
    }
    if (confirm("Would you like special characters in your password?")) {
        choiceArr = choiceArr.concat(specialCharArr);
    }
    if (confirm("Would you like numbers in your password?")) {
        choiceArr = choiceArr.concat(numberArr);
    }
    return true;
}

The function above completes a series of tasks that runs through the prompts that the user needs to interact with.

function generatePassword () {
var password = "";
for(var i = 0; i < characterLength; i++){
    var randomIndex = Math.floor(Math.random() * choiceArr.length);
    password = password + choiceArr[randomIndex];
  }
  return password;
}
The function above is what is actually creating our random password after the data from the user has been completed and processed. 

