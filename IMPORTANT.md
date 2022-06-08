## create react app 

-> npx create-react-app .      [. is for running the app in the same folder]

-> @import-normalize; [in css it takes care different defaults in different browser]


## Useful Extensions

1. ES7+ React/Redux/React-Native/JS snippets

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

3. window.addEventListener can be used when we need to keep track of changes in window

4. useEffect(function,optional argument which is an array)
   when we pass an empty array this means we only want to run this effect once when this component mounts.
   And we pass the values in the array in such a way that our logic inside the effect get a call on 
   the first render or change of these values.
   
   Always return a function from useEffect in order to clear up the previous effect
   In that return function, we should abort all the calls that we are making like api call, eventListener.

   Example 
    useEffect(() => {
        let canceled = false;
        setLoading(true);
        fakeFetch(person).then(data => {
        if (!canceled) { -> in order to avoid the race condition 
            setData(data);
            setLoading(false);
        }
        });
        return () =>{
            canceled=true;
            Abort API Call/RemoveEventListener;
        };
    }, [person]);

5. While rendering a array in react always pass an key which is unique because this will only render that part only not the whole array.

6. {...} spread operators are used in order to pass as it is.