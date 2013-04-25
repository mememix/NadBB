# NodeBB
**NodeBB** is a robust nodejs driven forum built on a redis database. It is powered by web sockets, and is compatible down to IE8.

## Installation

First step is to obtain all of the dependencies requires by NodeBB:

    $ npm install

*(Optional)* Next, we install redis. If you already have redis installed, you can skip this step.

    # apt-get install redis

Now we ensure that the configuration files are properly set up. NodeBB runs on port 4567 by default. The client side config can be set up thusly:

    $ cp public/config.default.json public/config.json

... and the server side config can be set up similarly:

    $ cp config.default.js config.js

Ensure that `/public/config.json` points to the publically accessible IP/hostname of your forum, and that the values of the server side config are also set correctly (see below).

Lastly, we run the forum.

    $ node app

## Server Configuration

The server configuration file (located at `/config.js`) contains default options required for the running of NodeBB. The following options are available:

<table>
	<tr>
		<th>Option</th>
		<th>Description</th>
	</tr>
	<tr>
		<td><b>base_url</b></td>
		<td><i>(Default: 'http://localhost')</i> A web-accessible URL to your app, without the port</td>
	</tr>
	<tr>
		<td><b>port</b></td>
		<td><i>(Default: 4567)</i> The default port that NodeBB runs on</td>
	</tr>
	<tr>
		<td><b>mailer</b></td>
		<td>
			<i>(Default: {<br />
				&nbsp;&nbsp;&nbsp;&nbsp;host: 'localhost',<br />
				&nbsp;&nbsp;&nbsp;&nbsp;port: '25',<br />
				&nbsp;&nbsp;&nbsp;&nbsp;from: 'mailer@localhost.lan'<br />
			})</i><br />
			Settings for the outgoing mailer (for emails involving user registration/password resets)
		</td>
	</tr>
</table>

## Client Configuration

As the client will utilise web sockets to connect to the server, you'll need to customise the client configuration file (located at `/public/config.json`) to point to your server's publically accessible IP. The port will be identical to the port specified in the server-side configuration (defaulted to `4567`).