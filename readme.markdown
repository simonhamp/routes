# Routes

Hi, thanks for checking out Routes! Routes is low-level PHP class for defining and using URL routing patterns similar to CodeIgniter. In fact Routes is based on [CodeIgniter's implementation](https://github.com/EllisLab/CodeIgniter/blob/develop/system/core/Router.php).

## Installation

You can install via Composer or grab the files and include whichever way you prefer.

    require { "simonhamp/routes": "1.0" }

## Usage

To use Routes, you simply need to place the class somewhere accessible within your application. Then you need to define some routes and register them:

    <?php
      include('inc/routes.php');
	
      Routes::add(array(
        'testing/(:num)' => 'test/$1',
        'posts/(:any)' => 'news/$1'
      ));

      $origin = 'testing/1';
      echo 'Origin: ' . $origin . '<br>';
      echo 'Reroute: ' . Routes::route( $origin );

## Why?

In-App Routing, as opposed to URL Rewriting (e.g. .htaccess/mod_rewrite), is a popular method for defining patterns for URLs in web sites and applications. It allows the developer to make an app appear one way, but underneath go another. It's most commonly found in MVC web frameworks (Rails, Sinatra, CakePHP, CodeIgniter et al). Routing is simple, but powerful, and could be really useful in situations outside of those frameworks.

There are [other](http://dev.horde.org/routes/) [attempts](http://routes.groovie.org/) at portable routing libraries, but they're too tied into the MVC framework schema to be useful outside. That's where Routes comes in. You could use it as your routing system for yet another framework or you can keep it completely separate.

Using Routes you can define complex routes using simple instructions and get the rewritten URL as a return variable in your code. So it doesn't need a specific web server. It doesn't do anything fancy, it just rewrites the URLs you give it according to the rules you supply, in the order you supplied them. Simple.

Hope you find it useful! :)

Questions? Comments? Feel free to [raise an issue](issues/new) or message me on Twitter [@simonhamp](http://twitter.com)
