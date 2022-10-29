<script>
    import Form from "./Form.svelte";
    export const random = Math.floor(Math.random() * (100 - 1)) + 1
    console.log(random)

    let temp = "or"
    let hint = "Enter a guess!"

    function processInput(event) {
        const guess = event.detail

        console.log("Recieved input: "+guess)

        if (guess > random) {
            console.log('guess is greater')
            console.log(random)
            hint = "Lower!"
            temp = "cold"
            
        }else if(guess < random) {
            console.log('guess is less')
            console.log(random)
            hint = "Higher!"
            temp = "hot"
        }
        else {
            console.log('GUESSEDDD!!! GG!!! WP!!!!!')
            console.log(random)
            hint = "You got it! (New number generated!)"
            temp = "or"
        }
    }
</script>

<h2 class={temp}>{hint}</h2>
<Form on:input={processInput}/>

<style>
  .hot {
    color: red;
    filter: drop-shadow(0 0 2.5px red);
  }
  .hot:hover {
    filter: drop-shadow(0 0 5px red);
    transition: 0.5s;
  }
  .hot:not(:hover) {
    transition: 0.5s;
  }
  .cold {
    color: skyblue;
    filter: drop-shadow(0 0 2.5px skyblue);
  }
  .cold:hover {
    filter: drop-shadow(0 0 5px skyblue);
    transition: 0.5s;
  }
  .cold:not(:hover) {
    transition: 0.5s;
  }
  .or:hover {
    filter: drop-shadow(0 0 2.5px white);
    transition: 0.5s;
  }
  .or:not(:hover) {
    transition: 5s;
  }
</style>