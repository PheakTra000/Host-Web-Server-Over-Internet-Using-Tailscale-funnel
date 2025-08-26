### ***Setting up the web server and host on local network***
	install Express:
		for arch `pacman -S npm && npm install express`
		for debian `apt install npm && npm install express`
	install Node:
		for arch `pacman -S nodejs`
		for debian `apt install nodejs`
		
- Create server directory:
	```
	mkdir webServer
	cd webServer
	nano server.js
	nano index.js
	```
	
- For `index.js`
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h2>This is my website</h2> // you webpage
</body>
</html>
```

- For `server.js`
```
const express = require('express');
const app = express();

app.use(express.static(__dirname));

app.listen(3000, () => console.log('Server running at http://localhost:3000'));
```
- Now you have this:
![[Pasted image 20250826151143.png]]
![image1](../asset/Screenshot From 2025-08-26 15-11-41.png)

- To run the server: `node server.js

___
### ***host the server over internet using tailscale: funnel***
First we need to host the local server first and save the port.

connect our machine to the tailscale server `sudo tailscale up`

use funnel to forward the port: `sudo funnel "port"`,   `sudo funnel 3000`
![[Screenshot From 2025-08-26 15-20-46.png]]



browse the link that funnel has created:
![[Pasted image 20250826152525.png]]
___
