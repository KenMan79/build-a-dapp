# Let’s Look at LNRChain

The LNRChain folder includes tendermint, and the basic app.js demo file, and is meant to be utilized for:
1. Part of a pipeline where you can connect Tendermint to BigChainDB *OR*
2. A [sidechain](https://medium.com/@jaekwon/cosmos-creating-interoperable-blockchains-part-1-2929435ba1fa) for the SDK and [LNRBeta](https://github.com/Lonero-Team/Lonero-Beta) and [Bitcoin](https://github.com/bitcoin/bitcoin).

To access LNRChain, if you are still in the GridBee folder:  
```
$ cd ../
$ cd ../
$ cd LNRChain
$ sudo chmod 777 tendermint
$ sudo nano app.js
```
Now you have just opened the app.js sample in the terminal, you should see:  
```
// app.js
let lotion = require('lotion')

let app = lotion({
    initialState: {
        count: 0
    }
})

function transactionHandler(state, transaction) {
    if (state.count === transaction.nonce) {
        state.count++
    }
}

let connect = require('lotion-connect')
app.use(transactionHandler)

app.start().then(appInfo => console.log(appInfo.GCI))
```  
This is Lotion’s multi-state sample file which allows you to run multiple states for the blockchain project you want to setup. Lotion is the npm module powered by the Tendermint consensus for you to make your own blockchain apps.
