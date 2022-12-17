<script>
    import Form from "./Form.svelte";
    import { Confetti } from "svelte-confetti"
    import Dopamine from "./Dopamine.svelte";
    import Counter from "./Counter.svelte";

    function generate(max) {
      const number = Math.floor(Math.random() * (max - 1)) + 1
      return number
    }

    function setbg(bg) {
      document.documentElement.style.setProperty('--bg', bg)
    }

    let random = generate()

    console.log(random)
    
    let amount
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
            setbg("skyblue")
            
        }else if(guess < random) {
            console.log('guess is less')
            console.log(random)
            hint = "Higher!"
            temp = "hot"
            setbg("red")
        }
        else {
            console.log(random)
            random = generate(100)
            hint = "You got it! (New number generated!)"
            temp = "or"
            amount = Math.floor(Math.random() * 50) + 150
            console.log("Amount: "+amount)
            setbg("#ffffff")
        }
    }
</script>

<h2 class={temp}>{hint}</h2>

<Form on:input={processInput}/>

<Dopamine amount={amount}/>

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

  :root {
    --bg: #ffffff;
    background-image: linear-gradient(to bottom right,#242424, 80%, var(--bg));
  }

</style>