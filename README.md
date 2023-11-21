// NUMBER GUESSING GAME

/////////////////////////////////////////////////////////////////////////////

const minNum = 50;
const maxNum = 100;

// Math.floor = abrunden 
// Math.random() ist immer eine zahl zwischen 0 und 1 auch mit mehreren nachkomma stellen bsp.(0,1) nie über 1!
// daher auch * rechnen  * (maxNum - minNum + 1) + minNum) bsp. *=0.1 (100 - 50 + 1) + minNum) 
// + 1 beduetet das die zahl erst ab 1 beginnt also hat keine rechnerische bedeutung (keine ahnung)
const zufallszahl = Math.floor(Math.random() * (maxNum - minNum + 1) + minNum);

console.log(zufallszahl);

/////////////////////////////////////////////////////////////////////////////

const minNum1 = 1;
const maxNum1 = 100;

let attempts = 0;44
let guess;
let running = true;

while(running){

    guess = window.prompt(`Guess a number between ${minNum1} - ${maxNum1}`)
    guess = Number(guess);

    if(isNaN(guess)){
        window.alert("Please enter a valid number");
    }

    else if(guess < minNum1 || guess > maxNum1){
        window.alert("Please enter a valid number!");
    }

    else{
        attempts++;
        if(guess < zufallszahl){
            window.alert("TOO LOW! TRY AGAIN!");
        }
        else if(guess > zufallszahl){
            window.alert("TOO HIGH! TRY AGAIN!");
        }
        else{
            window.alert(`CORRECT! The zufallszahl was ${zufallszahl}. It took you ${attempts} attempts`);
            running = false;
        }
    }
}
