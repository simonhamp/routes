# Routes

Hi, thanks for checking out Routes! Routes is low-level PHP class for defining and using URL routing patterns similar to CodeIgniter. In fact Routes is based on [CodeIgniter's implementation](https://github.com/EllisLab/CodeIgniter/blob/develop/system/core/Router.php).

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

Hope you find it useful! :)