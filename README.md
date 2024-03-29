**LAB Exercise - Algorand Hackathon Developer**

**Table of Contents**

[Getting Started for Hackathon 2](#getting-started-for-hackathon)

[Install Algorand node 2](#_Toc16786815)

[Verify your data directory 4](#_Toc16786816)

[Apply current updates 5](#apply-current-updates)

[Private network tutorials (optional)
5](#private-network-tutorials-optional)

[Download/Clone Algorand SDKs in your language of choice.
5](#_Toc16786819)

[Install VS Code or alternate IDE (optional)
7](#install-vs-code-or-alternate-ide-optional)

[Unzip the hackathon samples 8](#_Toc16786821)

[Replace tokens and addresses in the sample code.
11](#replace-tokens-and-addresses-in-the-sample-code.)

[Start two terminal sessions 12](#start-two-terminal-sessions)

[Install Postman or your favorite code-agnostic tool for REST API
testing (Paw… etc) (Optional) 13](#_Toc16786824)

[Getting started with Private Network (optional)
14](#getting-started-with-private-network-optional)

[Goal Command Line tools / AlgoExplorer.io
18](#goal-command-line-tools-algoexplorer.io)

[Goal 18](#goal)

[AlgoExplorer.io 20](#algoexplorer.io)

[SDKs 22](#sdks)

[JavaScript SDK 22](#bookmark=id.111kx3o)

[JavaScript SDK Sample webapp 23](#javascript-sdk-sample-webapp)

[Encode/Decode Note Field 29](#encodedecode-note-field)

[Node Example: Retrieving Latest Block Information
30](#node-example-retrieving-latest-block-information)

[More Examples 31](#more-examples)

[Go SDK 31](#bookmark=id.3ygebqi)

[kmdclient.go - kmd client go 35](#kmdclient.go---kmd-client-go)

[backupwallet.go - Backing up a Wallet
36](#backupwallet.go---backing-up-a-wallet)

[signsubmit.go - Signing and submitting a transaction
36](#signsubmit.go---signing-and-submitting-a-transaction)

[signoffline.go - Sign a transaction offline
36](#signoffline.go---sign-a-transaction-offline)

[submittransfilefrom.go - Submit the transaction from a file
36](#submittransfilefrom.go---submit-the-transaction-from-a-file)

[manipulatemultisig.go - Manipulating multisig transactions
36](#manipulatemultisig.go---manipulating-multisig-transactions)

[Java SDK 36](#java-sdk)

[GetBlock.java – gets the status and lastround
37](#getblock.java-gets-the-status-and-lastround)

[AccountTest.java - Generate account and backup phrase
38](#accounttest.java---generate-account-and-backup-phrase)

[NewWallet.java - kmd client 38](#newwallet.java---kmd-client)

[BackupWallet.java and RestoreWallet.java - Backing up and restoring a
Wallet
38](#backupwallet.java-and-restorewallet.java---backing-up-and-restoring-a-wallet)

[SignAndSubmit.java - Signing and submitting a transaction
39](#signandsubmit.java---signing-and-submitting-a-transaction)

[SignOffline.java - Sign a transaction offline
39](#signoffline.java---sign-a-transaction-offline)

[SubmitFromFile.java - Submit the transaction from a file
39](#submitfromfile.java---submit-the-transaction-from-a-file)

[GetAccountTransactions.java - Get account transactions
39](#getaccounttransactions.java---get-account-transactions)

[Multisig.Java - Manipulating multisig transactions
39](#multisig.java---manipulating-multisig-transactions)

[EncodeDecode.Java - Encode/decode Note Field This sample shows how to
encode and decode the Note Field to build Layer 2 solutions.
39](#encodedecode.java---encodedecode-note-field-this-sample-shows-how-to-encode-and-decode-the-note-field-to-build-layer-2-solutions.)

[Python SDK 39](#python-sdk)

[example.py 39](#example.py)

[Working with the Note Field: 43](#working-with-the-note-field)

[Resources 44](#resources)

# **Getting Started for Hackathon**

**  
Time Estimate: 1 hour**

This section provides guidance on installing an Algorand node and the
tools that will be useful in your hackathon efforts. Happy coding\!
Download algorandsamples.zip at
<http://github.com/algorand-devrel/hackathon> and unzip into a folder
off of your $HOME folder. In terminal type in echo $HOME to get your
Home folder location.

<span id="_Toc16786815" class="anchor"></span>**Install Algorand node  
**Time Estimate 10 minutes

In this section will install an Algorand node.

A synchronized node will be provided for this hackathon, however, you
need to install your own node, so you can do this lab exercise and
continue to work on the solution after the hackathon is over, as well as
build other solutions. Follow the instructions on how to install your
node are here:

<span class="underline"><https://developer.algorand.org/docs/introduction-installing-node>  
</span>

By default, an Algorand installation is configured to run on MainNet.
For most users, this is the desired outcome.  Developers, however, need
access to our TestNet or DevNet networks. This
[<span class="underline">guide</span>](https://developer.algorand.org/docs/switching-networks)
will walk you through how to switch networks, if you have not already
done so.

Your node may take a while to sync (several hours). You can proceed to
the following steps in the meantime, noting if the goal command does not
seem to be working, like transferring funds for example, it may be
because the node is not synced yet. To see if it is synced use this
command from terminal:

> goal node status -d \~/node/data

Note: When installing with DEB or RPM packages the binaries will be
installed in the /usr/bin and the data directory will be set to
/var/lib/algorand. It is advisable in these installs that you add the
following export to your shell config files.

> export ALGORAND\_DATA=/var/lib/algorand
> 
> When the Sync Time is zero consistently, it will be close to, if not
> all the way, synced.  
>   
> ![A screenshot of a cell phone Description automatically
> generated](images/media/image1.png)

**Alternatives**

The above process will take several hours to sync, so there are two
alternatives that can be used in the meantime. Each option provides an
Algod token and a Server URL. These values will be needed in your
solution code as well as the sample hackathon lab exercises.  
  
  
**Algorand Berlin Hackathon**  
  
**Option 1**

The API Token and Server address can be used in the Hackathon. Once the
hackathon is over, you will need to use your own node or one from
Purestake (see Option 2).

> API Token
> 
> ef920e2e7e002953f4b29a8af720efe8e4ecc75ff102b165e0472834b25832c1  
>   
> Server Address

<http://berlinhack.algodev.network:9100>

**Purestake Token**

**Option 2**

PureStake is offering up a token for this hackathon. You do not need to
register. This is free for use during the hackathon.

> After the Hackathon is over, you can register to receive a new token
> here:  
>   
> <https://www.purestake.com/algorand-api>
> 
> More details here:
> 
> <https://www.purestake.com/technology/algorand-services/>

***API-Key token for both TestNet and MainNet:  
***

> B3SU4KcVKi94Jap2VXkK83xx38bsv95K5UZm2lab
> 
> TestNet Server URL address:
> https://testnet-algorand.api.purestake.io/ps1
> 
> MainNet Server URL address:
> <https://mainnet-algorand.api.purestake.io/ps1>

Purestake offers many benefits including a Basic free tier as well as
Pro and Enterprise levels:

> Instant Access to Algorand API in Testnet and Mainnet

  - No wait for downloads and blockchain sync times

> API is backed by Full Archival Transaction Indexer Nodes

  - Full algod API with performant transaction queries

> Secure and Reliable Infrastructure

  - Automated Highly Available Infrastructure, Managed 24x7x365

<span id="_Toc16786816" class="anchor"></span>**Verify your data
directory**  
  
To verify where your data directory is and that you are running TestNet,
use these two commands:

1.  ps aux | grep algod

> ![A close up of a mans face Description automatically
> generated](images/media/image2.png)

2.  goal node status -d \~/node/data

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image3.png)

## Apply current updates

> cd \~/node
> 
> ./update.sh -d \~/node/data

## Private network tutorials (optional)

> Time Estimate - 5 minutes **  
> **  
> If are new to Algorand, it may be useful to spend some time doing the
> Private Network tutorials.
> 
> These tutorials will get you familiar with many of the Goal commands
> in a Private Network that you would be using to develop you solution.
> The purpose of the Private Network is to facilitate developers with a
> testing/learning environment without having to use TestNet or MainNet.
> 
> To get started in creating a Private network, in this document, see
> [<span class="underline">Getting started with the Private
> Network</span>](#section-1), (Estimated time 5 minutes)

<span id="_Toc16786819" class="anchor"></span>**Download/Clone Algorand
SDKs in your language of choice.  
  
These are the SDKs available to date. More are on the way. \*\***  
Time Estimate - 10 minutes

  - Go, see install notes here
    [<span class="underline">https://github.com/algorand/go-algorand-sdk</span>](https://github.com/algorand/go-algorand-sdk)
    
      - See Go SDK documentation here:
        [<span class="underline">https://godoc.org/github.com/algorand/go-algorand-sdk</span>](https://godoc.org/github.com/algorand/go-algorand-sdk)

  - Python, see install notes here
    [<span class="underline">https://github.com/algorand/py-algorand-sdk</span>](https://github.com/algorand/py-algorand-sdk)
    
      - See Python SDK documentation here:
        [<span class="underline">https://py-algorand-sdk.readthedocs.io/en/latest/</span>](https://py-algorand-sdk.readthedocs.io/en/latest/)

  - Java, see install notes here
    [<span class="underline">https://github.com/algorand/java-algorand-sdk</span>](https://github.com/algorand/java-algorand-sdk)
    
      - See Java documentation here
        <span class="underline"><https://algorand.github.io/java-algorand-sdk/> </span>

<!-- end list -->

  - JavaScript, see install notes here
    [<span class="underline">https://github.com/algorand/js-algorand-sdk</span>](https://github.com/algorand/js-algorand-sdk)
    
      - See JavaScript SDK documentation
        visit [<span class="underline">https://developer.algorand.org</span>](https://developer.algorand.org/)

> \*\* If you do not see your language of choice, we have two swagger
> files that you can load in at
> [<span class="underline">https://app.swaggerhub.com</span>](https://app.swaggerhub.com/)
> to generate your own client. The swagger definition json files are for
> Algod and kmd. These swagger.json files can also be loaded into code
> agnostic tools such as
> [<span class="underline">Postman</span>](https://www.getpostman.com/downloads/)
> or [<span class="underline">Paw</span>](https://paw.cloud/) for REST
> API testing. To generate the latest swagger definitions, use the
> following commands…
> 
> For **Alogd** use:
> 
> [<span class="underline">http://localhost:8080/swagger.json</span>](http://localhost:8080/swagger.json)  
> or
> 
> curl http://$(cat \~/node/data/algod.net)/swagger.json \>
> swagger.json  
> (this will appear in your node folder)
> 
> For **kmd** use:
> 
> [<span class="underline">http://localhost:7833/swagger.json</span>](http://localhost:7833/swagger.json)
> 
> or
> 
> curl http://$(cat \~/node/data/kmd-v0.5/kmd.net)/swagger.json \>
> swaggerkmd.json
> 
> (this will appear in your node folder)
> 
> Then import at
> [<span class="underline">https://app.swaggerhub.com</span>](https://app.swaggerhub.com/)
> and select CodeGen Options for the Client SDK in the desired language
> 
> ![A screenshot of a cell phone Description automatically
> generated](images/media/image4.png)

## Install VS Code or alternate IDE (optional)  

**Install an Integrated Development Environment for coding and debugging
JavaScript, Java, Go and/or Python solutions (optional)**

Time Estimate - 10 minutes

> There are many IDEs to debug many languages. This lab exercise uses
> <span class="underline">[Visual Studio Code on the
> Mac](https://docs.microsoft.com/en-us/visualstudio/mac/?view=vsmac-2019)
> (and many other platforms)</span>. If you are familiar with Visual
> Studio, many of the keyboard shortcuts also work in VS Code too.
> Install the extensions for each language and VS Code facilitates:

  - > Debugging

  - > Intellisense

  - > Workspace support to easily load and run each demo

> Search on each language extension one at a time and install in VS Code
> .

  - > Go

  - > Python

  - > Java

  - > JavaScript

Should you decide to use VS Code, your extensions list should look
something like this:

> ![A screenshot of a computer Description automatically
> generated](images/media/image5.png)

<span id="_Toc16786821" class="anchor"></span>**Unzip the hackathon
samples**  
  
  
Time Estimate - 5 minutes  
  
From <http://github.com/algoand-devrel/hackathon> Download/Clone the
Hackathon repository which has the algorandsamples.zip file and this
document in the readme.md, Unzip into a folder off of your $HOME folder

In terminal type in echo $HOME to get your Home folder location. The
contents should look similar to this:

![A screenshot of text Description automatically
generated](images/media/image6.png)**  
**

## Replace tokens and addresses in the sample code. 

Time Estimate - 10 minutes

Follow the SDK install directions for each in the readme files. In all
of the examples, at some point, you will need to replace the code
placeholders with the Algod and Kmd tokens and network addresses in
each. For the node you created, these can be found here…

> From your node directory copy off values in /data for:

  - > algod.token

  - > algod.net

> From your node directory copy off values in /data/kmd-v0.5 for:

  - > kmd.token

  - > kmd.net

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image7.png)

For example, in the JavaScript SDK sample webapp test.js file update the
constants with these values:

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image8.png)

## Start two terminal sessions 

  - In the first one, start localhost using
    [<span class="underline">http-server</span>](https://www.npmjs.com/package/http-server):
    Navigate to algorandsamples folder with finder and right click to
    start terminal session in that folder. Then enter:

> http-server

  - In the other terminal session, navigate to \~/node and start up kmd
    and node (kmd may time out after a while, so don’t just assume it is
    running.)

> goal node start -d \~/node/data
> 
> goal kmd start -d \~/node/data

# 

<span id="_Toc16786824" class="anchor"></span>**Install Postman or your
favorite code-agnostic tool for REST API testing (Paw… etc) (Optional)  
  
**Time Estimate - 10 minutes

When having a team of hackers, it might be useful to communicate API
discussions with a code agnostic tool, as team members may have
different programming skill sets.

1.  [<span class="underline">https://www.getpostman.com/</span>](https://www.getpostman.com/)

2.  To get the latest Algorand swagger.json files use these commands
    from terminal:

> goal node start -d \~/node/data  
>   
> goal kmd start -d \~/node/data  
>   
>   
> curl http://$(cat \~/node/data/algod.net)/swagger.json \> swagger.json
> 
> curl http://$(cat \~/node/data/kmd-v0.5/kmd.net)/swagger.json \>
> swaggerkmd.json

3.  Import these Json swagger files into Postman

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image9.png)

4.  Make these changes to the request:

<!-- end list -->

1.  Click on GET current status node command.

2.  Change http://localhost to
    [<span class="underline">http://127.0.0.1:8080</span>](http://127.0.0.1:8080)
    for algod or
    [<span class="underline">http://127.0.0.1:7833</span>](http://127.0.0.1:7833)
    for kmd

3.  Add header key and value ([<span class="underline">info
    here</span>](https://developer.algorand.org/docs/using-sdks-and-rest-apis))  
    The API Token for the algod process is named X-Algo-API-Token and
    the kmd's is named X-KMD-API-Token.

4.  Press Send to send the request

5.  See the response

> ![A screenshot of a social media post Description automatically
> generated](images/media/image10.png)

# 

# **Getting started with Private Network (optional)**

5 Minutes

In this section you will learn how to create a Private Network. A
Private Network is for developers. It allows you to learn Algorand
Blockchain without having to touch either TestNet or MainNet. Code using
the Algorand SDKs, can be used to access the Private Network.  
  
This exercise is suggested for developers that are just getting started
with Algorand.

Note: the [<span class="underline">Algorand TestNet
Dispenser</span>](https://bank.testnet.algorand.network/), a tool used
to send Algos to an account, only works for TestNet and not a Private
Network.

1)  Navigate to the algorandsamples folder

2)  Open networktemplate.json in VS Code and review. Note the Primary
    and Node Nodes that will be created.

> ![A close up of a map Description automatically
> generated](images/media/image11.png)

3)  In Finder, navigate to your root directory and show the directory
    structure does not have folders for Node and Primary.

4)  Run this command in Terminal from the node folder to create the
    private network.

> **goal network create -r \~/net1 -n private -t networktemplate.json**

![A screenshot of a cell phone Description automatically
generated](images/media/image12.png)

> **goal network start -r \~/net1**
> 
> **goal network status -r \~/net1**

![A screenshot of a social media post Description automatically
generated](images/media/image13.png)

5)  Open Finder and look at the directory structure for /net1/Node and
    /net1/Primary  
      
    ![A screenshot of a cell phone Description automatically
    generated](images/media/image14.png)

6)  (Optional) The full set of Private Network tutorials are here:
    [<span class="underline">https://developer.algorand.org/docs/tutorials</span>](https://developer.algorand.org/docs/tutorials).
    This is a great learning resource.

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image15.png)

Go to
<span class="underline"><https://developer.algorand.org/docs/creating-new-account-and-participation-key></span>
to complete all the rest of the tasks in this tutorial including:

  - Creating a new wallet

  - Creating a new Account and Participation key

  - Write a raw transaction and post to algod REST server

  - Creating a multisig account

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image16.png)

7)  Once finished you can delete the private network as this is for
    learning only and cannot be used for further development, other than
    testing with SDK code. Delete the Private Network

> **goal network delete -r \~/net1**

# **Goal Command Line tools / AlgoExplorer.io**  

Time Estimate - 10 minutes

In this section we will show how to use the goal command line tool as
well as the AlgoExplorer.io.

## Goal

The goal command line tool provides access to these objects, methods and
properties.

> ![A screenshot of a computer Description automatically
> generated](images/media/image17.png)

1.  To start a node use this command:

> goal node start -d \~/node/data  
>   
> You may need to use this command depending on your path environment
> variable.
> 
> ./goal node start -d \~/node/data

2.  To start kmd use this command:  
      
    goal kmd start -d \~/node/data

3.  To get help with goal use this command:  
      
    goal -h  
      
    ![A screenshot of a social media post Description automatically
    generated](images/media/image18.png)

4.  To get help with and command

> goal \[command\] -h  
>   
> For example, us this command to get help with node
> 
> goal node -h
> 
> ![A screenshot of a cell phone Description automatically
> generated](images/media/image19.png)

5.  Run this to get a status. We will copy off the block number, for
    subsequent use in AlgoExplorer:

> goal node status -d \~/node/data

6.  Copy last committed block

![A screenshot of a cell phone Description automatically
generated](images/media/image20.png)

## AlgoExplorer.io

The AlgoExplorer can be used to search on blocks, transactions and
account addresses in either MainNet or TestNet.

1.  Browse to <span class="underline">[
    https://algoexplorer.io/](https://algoexplorer.io/)</span>

2.  Click on TestNet in the dropdown

![A screenshot of a cell phone Description automatically
generated](images/media/image21.png)

3.  Paste in block, press search, click on transactions. If you do not
    see any transactions, use this block: 868921

![A screenshot of a cell phone Description automatically
generated](images/media/image22.png)

4.  Click on TxID

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image23.png)

5.  Drill into a transaction and notice Sender / receiver / note /
    status / amount / fees and other fields.

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image24.png)

# **SDKs**

> **  
> Click to go to your desired SDK  
> **
> 
> <span class="underline">[JavaScript SDK](#bookmark=id.111kx3o)  
> </span>

<span class="underline">[Go SDK](#bookmark=id.3ygebqi)  
</span>

> [<span class="underline">Java SDK</span>](#java-sdk)
> 
> [<span class="underline">Python SDK</span>](#python-sdk)
> 
> <span id="bookmark=id.111kx3o" class="anchor"></span>**JavaScript
> SDK  
> **Time Estimate - 20 minutes
> 
> In this section, we use the sample web app that comes with the
> Algorand JavaScript SDK.

1)  For the JavaScript samples, open folder for myjsdemo into VS Code or
    you favorite IDE  
      
    Or just open the js.code-workspace in the algorandsamples folder
    with VS Code.

2)  The JavaScript launch.json file should be similar to this

![A screenshot of a social media post Description automatically
generated](images/media/image25.png)

### JavaScript SDK Sample webapp

3)  JavaScript AlgoSDK is a JavaScript library for communicating with
    the Algorand network for modern browsers and node.js. Navigate to
    the Algorand JavaScript GitHub repository to clone or download and
    note to the examples/webapp folder. This is the code we will use to
    learn the JavaScript SDK from.

[<span class="underline">https://github.com/algorand/js-algorand-sdk</span>](https://github.com/algorand/js-algorand-sdk)

![A screenshot of a cell phone Description automatically
generated](images/media/image26.png)

4)  Install the JavaScript SDK using the instructions on the readme
    file.

5)  You make need to update the algosdk.min.js that is included in the
    demo zip, from the SDK clone/zip. But, if you do update, use the
    sample code on GitHub to stay in sync.

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image27.png)

6)  Run thru debugger with localhost (launch.json file below) or just
    bring up Finder and double click on Test.html.

7)  Your launch.json file should look similar to this if running
    localhost:

> ![A screenshot of a social media post Description automatically
> generated](images/media/image25.png)

8)  **Run sample by navigating to the test.html page and click on
    buttons in this order:**

<!-- end list -->

1.  > Get Latest Block

2.  > Generate Account

3.  > Get Account Details - note the amount as 0, need to add money –
    > copy off account

4.  > TestNet Dispenser – paste account

5.  > Recover Account from Mnemonic

6.  > Get Account Details – note the amount (it may take a few seconds
    > to show up)

7.  > Submit a transaction (send money)

8.  > Get Tx From Account (TX ID) (this may take 4 or 5 seconds to show
    > up)

Screen shots:

1.  Get Latest Block

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image28.png)

2.  Generate Account

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image29.png)

3.  Get Account Details

> ![A screenshot of a social media post Description automatically
> generated](images/media/image30.png)

4.  Algorand TestNet Dispenser

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image31.png)

5.  Recover Account from Account Mnemonic

6.  If amount does not show up – press Get Account Details after a few
    seconds

> ![A screenshot of a social media post Description automatically
> generated](images/media/image32.png)

7.  Submit Transaction

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image33.png)

8.  Get Tx From Account

> ![A screenshot of a cell phone Description automatically
> generated](images/media/image34.png)

9)  **Walk thru code in code in** **test.js** and **see each function we
    just used**.  
      
    All of this functionality is accomplished in a little over 200 lines
    of code\! How about that\!” (Applause) ☺

<!-- end list -->

1.  Open test.js

2.  Note atoken

3.  Note kmdtoken

4.  If running localhost, see debug console output after scrolling thru
    code, this should be the same as seen when running the demo.

![A screenshot of a social media post Description automatically
generated](images/media/image35.png)

### Encode/Decode Note Field

10) Two other function to note in the code are for encoding and decoding
    the free form Note Field. This field is used to create Layer 2
    solutions. Encode it on submit transaction and decode it when
    needed.

<!-- end list -->

1)  Open test.js

2)  Locate the submit transaction code

3)  Look for the encodeObj method

![A screenshot of a social media post Description automatically
generated](images/media/image36.png)

1)  Open test.js

2)  Locate the get transaction note code

3)  Look for the decodeObj method

![A screenshot of a cell phone Description automatically
generated](images/media/image37.png)

### Node Example: Retrieving Latest Block Information  

11) To retrieve the latest block’s information using Node, you would use
    the algod client wrapper functions shown below.

const algosdk = require('algosdk');

//Retrieve the token, server and port values for your installation in
the algod.net

//and algod.token files within the data directory

const atoken = "your token here";

const aserver = "http://127.0.0.1";

const aport = 8080;

const algodclient = new algosdk.Algod(atoken, aserver, aport);

(async () =\> {

let lastround = (await algodclient.status()).lastRound;

let block = (await algodclient.block(lastround));

console.log( block );

})().catch(e =\> {

console.log(e);

});

### More Examples  

12) See
    [<span class="underline">https://developer.algorand.org/docs/javascript-sdk</span>](https://developer.algorand.org/docs/javascript-sdk)
    for more samples.

> [<span class="underline">Web App: Client Wrapper
> Functions</span>](https://developer.algorand.org/docs/javascript-sdk#webapp-client)
> 
> [<span class="underline">Node: Retrieving Latest Block
> Information</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-latest)
> 
> [<span class="underline">Node: Creating a New Wallet and Account Using
> kmd</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-create-wallet)
> 
> [<span class="underline">Node: Backing Up and Restoring a
> Wallet</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-backup-wallet)
> 
> [<span class="underline">Node: Signing and Submitting a
> Transaction</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-sign)
> 
> [<span class="underline">Node: Locating a
> Transaction</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-find-transaction)
> 
> [<span class="underline">Node: Writing to the Note Field of a
> Transaction</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-note-write)
> 
> [<span class="underline">Node: Reading the Note Field of a
> Transaction</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-note-read)
> 
> [<span class="underline">Node: Creating a Multisignature Account and
> Signing a
> Transaction</span>](https://developer.algorand.org/docs/javascript-sdk#node-example-multisig)

13) [**<span class="underline">Skip to next
    section</span>**](#_heading=h.28h4qwu)

> <span id="bookmark=id.3ygebqi" class="anchor"></span>**Go SDK  
> **Time Estimate - 20 minutes

1)  **If using GO, Add the algorandsamples (or the directory you
    unzipped the hackathon code samples to) to the GOPATH environment
    variable**

Add these two line by editing your bash\_profile and then restart your
IDE and terminal sessions:  
  
GOPATH=\~/go:\~/algorandsamples/mygodemo/

export GOPATH

2)  To edit the .bash\_profile to add the above statements, quit
    and restart terminal and Visual Studio Code. This file is located
    in your home directory and you may need to type in command + shift +
    . to see it in Finder or opening the file in your editor, as it is
    hidden. 

3)  **For the Go samples, open folder for mygodemo into VS Code or you
    favorite IDE  
    **  
    Or just open the go.code-workspace in the algorandsamples folder
    with VS Code. **  
    **

4)  The Go **launch.json** file should be similar to this:

![A screenshot of a social media post Description automatically
generated](images/media/image38.png)

5)  In this step we will create an algodclient using the Go SDK. We will
    create the algod client and fetch node status information, and then
    a specific block. Optional Go samples are listed below as well.

6)  In the algorandsamples folder Open go.code-workspace or the mygocode
    folder in VS Code

If you have not already done so, Download/clone the Go SDK from:

[<span class="underline">https://github.com/algorand/go-algorand-sdk</span>](https://github.com/algorand/go-algorand-sdk)

7)  **Review the readme file:**

![A screenshot of a social media post Description automatically
generated](images/media/image39.png)

8)  **In VS Code, open algodclient.go in the VS Code Explorer**

![A screenshot of a cell phone Description automatically
generated](images/media/image40.png)

9)  Your launch.json file should look similar to this:

![A screenshot of a social media post Description automatically
generated](images/media/image41.png)

1.  Select the debugger

2.  Note algodToken

3.  Note MakeClient

4.  Note Status

5.  Run (you may be prompted to open launch.json. After it opens, then
    you need to go back and select algodclient.go again in the Explorer)

6.  Note status info in the debug console

![A screenshot of a cell phone Description automatically
generated](images/media/image42.png)

10) The debug console should show results for creating an algod client,
    algod status and block information.

11) Run as many of the following samples as desired, in this order
    (there is a file for each in a folder in the algosamples/mygodemo
    folder):

### kmdclient.go - kmd client go

The following example creates a wallet and generates an account within
that wallet. This account can now be used to sign transactions, but you
will need some funds to get started. If you are on the test network,
TestNet, you can use
the <span class="underline">[dispenser](https://bank.testnet.algorand.network/) </span>to
seed your account with some Algos.

### backupwallet.go - Backing up a Wallet 

You can export a master derivation key from the wallet and convert it to
a mnemonic phrase in order to back up any generated addresses. This
backup phrase will only allow you to recover wallet-generated keys; if
you import an external key into a kmd-managed wallet, you'll need to
back up that key by itself in order to recover it.

To restore a wallet, convert the phrase to a key and pass it
to CreateWallet. This call will fail if the wallet already exists:

### signsubmit.go - Signing and submitting a transaction

The following example shows how to to use both KMD and Algod when
signing and submitting a transaction. You can also sign a transaction
offline, which is shown in the next section of this document.

### signoffline.go - Sign a transaction offline

The following example shows how to create a transaction and sign it
offline. You can also create the transaction online and then sign it
offline.

### submittransfilefrom.go - Submit the transaction from a file 

This example takes the output from the previous example (file containing
signed transaction) and submits it to Algod process of a node.

### manipulatemultisig.go - Manipulating multisig transactions 

Here, we first create a simple multisig payment transaction, with three
public identities and a threshold of 2.

[**<span class="underline">Skip to next section</span>**](#resources)

## Java SDK

Time estimate: 20 minutes

1)  **For the Java samples open folder for java-test into VS Code or you
    favorite IDE  
    **  
    Or just open the java.code-workspace in the algorandsamples folder
    with VS Code.

2)  The Java **launch.json** file should be similar to this:

![A screenshot of a cell phone Description automatically
generated](images/media/image43.png)

3)  In this section we will get a block and display the info using the
    Java SDK. We will create the algod client and fetch node status
    information of the latest block. (Other code functions are
    optional).

4)  Show the Go SDK at:

> [<span class="underline">https://github.com/algorand/go-algorand-sdk</span>](https://github.com/algorand/go-algorand-sdk)

### GetBlock.java – gets the status and lastround

1.  Open the GetBlock.java file

2.  Note the call to getStatus

3.  Note the call to getLastRound

4.  Run

5.  Note the Output Console Display of the latest block

![A screenshot of a social media post Description automatically
generated](images/media/image44.png)

5)  Run as many of the following scripts as desired, in this order
    (there is a file for each in a folder):

### AccountTest.java - Generate account and backup phrase 

This example creates a random account, a backup phrase and performs a
recovery

This account can now be used to sign transactions, but you will need
some funds to get started. If you are on the test network, TestNet, you
can use
the <span class="underline">[dispenser](https://bank.testnet.algorand.network/) </span>to
seed your account with some Algos.

### NewWallet.java - kmd client 

The following example creates a wallet and generates an account within
that wallet. This account can now be used to sign transactions, but you
will need some funds to get started. If you are on the test network,
TestNet, you can use
the <span class="underline">[dispenser](https://bank.testnet.algorand.network/) </span>to
seed your account with some Algos.

### BackupWallet.java and RestoreWallet.java - Backing up and restoring a Wallet 

You can export a master derivation key from the wallet and convert it to
a mnemonic phrase in order to back up any generated addresses. This
backup phrase will only allow you to recover wallet-generated keys; if
you import an external key into a kmd-managed wallet, you'll need to
back up that key by itself in order to recover it.

To restore a wallet, convert the phrase to a key and pass it
to CreateWallet. This call will fail if the wallet already exists:

### SignAndSubmit.java - Signing and submitting a transaction 

The following example shows how to use both KMD and Algod when signing
and submitting a transaction. You can also sign a transaction offline,
which is shown in the next section of this document.

### SignOffline.java - Sign a transaction offline 

The following example shows how to create a transaction and sign it
offline. You can also create the transaction online and then sign it
offline.

### SubmitFromFile.java - Submit the transaction from a file 

This example takes the output from the previous example (file containing
signed transaction) and submits it to Algod process of a node.

### GetAccountTransactions.java - Get account transactions 

This example gets transactions for an account.

###  Multisig.Java - Manipulating multisig transactions

Here, we first create a simple multisig payment transaction, with three
public identities and a threshold of 2.

### EncodeDecode.Java - Encode/decode Note Field  
  
This sample shows how to encode and decode the Note Field to build Layer 2 solutions.  

[**<span class="underline">Skip to next section</span>**](#resources)

##   
Python SDK

Time estimate: 20 minutes

###   
example.py

1)  **For the Python samples open folder for mypythondemo into VS Code
    or you favorite IDE  
    **  
    Or just open the python.code-workspace in the algorandsamples folder
    with VS Code.

2)  The Python **launch.json** file should be similar to this:

![A screenshot of a social media post Description automatically
generated](images/media/image45.png)

3)  If not already done, clone or download the Python SDK at:

> [<span class="underline">https://github.com/algorand/py-algorand-sdk</span>](https://github.com/algorand/py-algorand-sdk)

4)  Use the instructions on the readme file to install the SDK

5)  In this section we will run the example.py code from the SDK. Before
    running example.py start kmd and alogd using these goal commands:  
      
    goal kmd start -d \[data directory\]  
      
    goal node start -d \[data directory\]

6)  Next, create a wallet and account, and copy off account address.

goal wallet new \[wallet name\] -d \[data directory\]  
  
goal account new -d \[data directory\] -w \[wallet name\]

7)  Paste the account address into the [Algorand
    <span class="underline">TestNet
    D</span>ispenser](https://bank.testnet.algorand.network/) to send
    Algos to this account.

8)  Edit params.py and add token information and data-dir-path  
      
    1\) Edit params.py  
    2\) Add token info for algod and kmd  
    3\) Add your data directory path

![A screenshot of a cell phone Description automatically
generated](images/media/image46.png)

9)  Edit example.py  
      
    1\) Edit example.py  
    2\) Uncomment Enter your Wallet, password and account info  
    3\) Comment prompt for these values  
    4\) Run the code and see the results in the Output console

![A screenshot of a cell phone Description automatically
generated](images/media/image47.png)

10) The example code performs the following functions:  
      
    Create kmd and algod clients

> Create a new kmd wallet
> 
> Generate an account and import to wallet
> 
> Get the mnemonic
> 
> Get last block
> 
> Create a transaction
> 
> Sign a transaction with kmd
> 
> Sign a transaction with account
> 
> Send the transaction

To see the new wallet and accounts we created use:

goal wallet list -w \[wallet name\] -d data

You should see something like this:

![A close up of a device Description automatically
generated](images/media/image48.png)

goal account list -w \[wallet name\] -d data

You should see something like this:

![A close up of a device Description automatically
generated](images/media/image49.png)

Other examples – (optional)

Using the Wallet class
[<span class="underline">https://github.com/algorand/py-algorand-sdk\#using-the-wallet-class</span>](https://github.com/algorand/py-algorand-sdk#using-the-wallet-class)

Backing up a wallet with mnemonic
[<span class="underline">https://github.com/algorand/py-algorand-sdk\#backing-up-a-wallet-with-mnemonic</span>](https://github.com/algorand/py-algorand-sdk#backing-up-a-wallet-with-mnemonic)

Recovering a wallet using a backup phrase
[<span class="underline">https://github.com/algorand/py-algorand-sdk\#recovering-a-wallet-using-a-backup-phrase</span>](https://github.com/algorand/py-algorand-sdk#recovering-a-wallet-using-a-backup-phrase)

Writing transactions to file
[<span class="underline">https://github.com/algorand/py-algorand-sdk\#writing-transactions-to-file</span>](https://github.com/algorand/py-algorand-sdk#writing-transactions-to-file)

Manipulating multisig transactions
[<span class="underline">https://github.com/algorand/py-algorand-sdk\#manipulating-multisig-transactions</span>](https://github.com/algorand/py-algorand-sdk#manipulating-multisig-transactions)

### Working with the Note Field:

[<span class="underline">https://github.com/algorand/py-algorand-sdk\#working-with-notefield</span>](https://github.com/algorand/py-algorand-sdk#working-with-notefield)

##   

[**<span class="underline">Skip to next section</span>**](#resources)

**  
**

# **Resources**

**More resources can be found here:**

AlgoExplorer.io

  - [<span class="underline">https://algoexplorer.io/</span>](https://algoexplorer.io/)

Algorand GitHub

  - [<span class="underline">https://github.com/algorand</span>](https://github.com/algorand)

Algorand TestNet Dispenser

  - [<span class="underline">https://bank.testnet.algorand.network/</span>](https://bank.testnet.algorand.network/)

Developer Portal

  - [<span class="underline">https://developer.algorand.org/</span>](https://developer.algorand.org/docs/developer-faq)

Developer FAQs

  - [<span class="underline">https://developer.algorand.org/docs/developer-faq</span>](https://developer.algorand.org/docs/developer-faq)

Forums

  - [<span class="underline">https://forum.algorand.org/</span>](https://forum.algorand.org/)

Community Portal – Events, Blog, Chapters, etc

  - [<span class="underline">https://community.algorand.org/</span>](https://community.algorand.org/)

Community Ambassador program

  - [<span class="underline">https://community.algorand.org/ambassadors/</span>](https://community.algorand.org/ambassadors/)

Swagger hub

  - [<span class="underline">https://swagger.io/tools/swaggerhub/</span>](https://swagger.io/tools/swaggerhub/)

Algorand Foundation Roadmap

  - [<span class="underline">https://algorand.foundation/roadmap</span>](https://algorand.foundation/roadmap)

Token Dynamics

  - [<span class="underline">https://algorand.foundation/token-dynamics</span>](https://algorand.foundation/token-dynamics)

YouTube Algorand

  - [<span class="underline">https://www.youtube.com/algorand</span>](https://www.youtube.com/algorand)

Consensus 2019 videos - Turing award winner - Silvio Micali keynote - is
in the second group (Construct) \#55 - Building the Technical Innovation
Required for a New Borderless Economy

  - [<span class="underline">https://www.coindesk.com/events/consensus-2019/videos</span>](https://www.coindesk.com/events/consensus-2019/videos)

![A screenshot of a social media post Description automatically
generated](images/media/image50.png)

More resources here:

  - Go
    [<span class="underline">https://golang.org/doc/install</span>](https://golang.org/doc/install).

  - Python
    [<span class="underline">www.python.org/downloads</span>](http://www.python.org/downloads)

  - Maven  
    [<span class="underline">http://www.codebind.com/mac-osx/install-maven-mac-os/</span>](http://www.codebind.com/mac-osx/install-maven-mac-os/)

> or
> 
> [<span class="underline">https://www.baeldung.com/install-maven-on-windows-linux-mac</span>](https://www.baeldung.com/install-maven-on-windows-linux-mac)

  - Java  
    [<span class="underline">https://www.oracle.com/technetwork/java/javase/downloads/index.html</span>](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

  - Enable JavaScript in browsers
    [<span class="underline">https://www.techwalla.com/articles/how-to-enable-javascript-on-a-mac</span>](https://www.techwalla.com/articles/how-to-enable-javascript-on-a-mac)

  - Install Node JS for localhost server
    [<span class="underline">https://www.npmjs.com/package/http-server</span>](https://www.npmjs.com/package/http-server)

#
