## create react app 

-> npx create-react-app .      [. is for running the app in the same folder]

## Important Point

1.  setState, useState are async function

    i.e always use previousState to setup a new state

    this.setState((prevState)=>{
        return {
            count:prevState+amount;
        }
    })


2. createContext can be used for creating global variables
   i.e. by using createContext variables that we create are available to all the nested components 