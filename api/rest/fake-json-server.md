# Fake JSON Server

{% hint style="warning" %}
Prerequisites: [NodeJS installed](../../windows-dev-setup/untitled.md#node-js).
{% endhint %}

Open up VS Code and switch to WSL-Ubuntu-20.04.

Open up Windows terminal -&gt; Ubuntu:

* Navigate to /home/&lt;your username folder&gt;
* `sudo mkdir JSONSERVER`
* `cd JSONSERVER`
* `code .`

In VS Code open up integrated terminal:

* To create package.json file as a mnifest file for our node.js app
  * `sudo npm init`
    * Hit enter to accept defaults
* to install json-server:
  * `npm install --save json-server`
  * create file db.json and put some value-key pairs
  * add these lines in package.json under scripts section:
    * "json:server": "json-server --watch db.json", 
    * "json:server:remote": "json-server [https://jsonplaceholder.typicode.com/db](https://jsonplaceholder.typicode.com/db)"

![](../../.gitbook/assets/image%20%2821%29.png)

Now we can run our json server with local and remote db:

For local db run `npm run json:server`

![](../../.gitbook/assets/image%20%2823%29.png)

For the remote one run: `npm run json:server:remote`

![](../../.gitbook/assets/image%20%2827%29.png)

