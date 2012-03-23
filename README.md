## CakePHP-2.x-Twitter-Plugin

This is a plugin for CakePHP to connect your app with the Twitter API using OAuth.
With this plugin it's possible to access the main API methods (such as status updates, timelines or user) of the Twitter API in all of your controllers. You even have the opportunity to make custom API-Calls with this plugin.

### Usage

* Upload to app/Plugin/Twitter
* Rename Config/twitter.default.php to Config/twitter.php
* Update the config file with your twitter app keys
* Go to YOURSITE/twitter/twitter/connect
* Put some code that will send an update to Twitter in another controller (maybe something like...)

public function afterSave($created) {
	$oauth_token = [either a session or from where the token is saved in db];
	$oauth_token_secret = [either a session or from where the token is saved in db];
	$this->Behaviors->load('Twitter.Twitter', array(
		'oauthToken' => $oauth_token, 
		'oauthTokenSecret' => $oauth_token_secret,
		));
	$this->updateStatus('Some message you want to tweet');
}

The plugin uses 'http_socket_oauth' (https://github.com/neilcrookes/http_socket_oauth) by Neil Crookes <www.neilcrookes.com> as extension for the CakePHP 'HttpSocket'. 

NOTE: This plugin does not support the "Twitter for Websites" Features (https://dev.twitter.com/docs/twitter-for-websites) like follow buttons or direct authentication.


### Requirements:

* PHP Version: 5.2+
* CakePHP Version: 2.0 Stable
* A Twitter (API) app (Registration: https://dev.twitter.com/apps/new)

### Additional Links From Original Fork:

https://github.com/fnitschmann/CakePHP-Twitter-Plugin/wiki/Installation
https://github.com/fnitschmann/CakePHP-Twitter-Plugin/wiki/Function-Reference
https://wiki.github.com/fnitschmann/CakePHP-Twitter-Plugin

@license MIT License (http://www.opensource.org/licenses/mit-license.php)
