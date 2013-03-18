curly [![Build Status](https://secure.travis-ci.org/ehough/curly.png)](http://travis-ci.org/ehough/curly)
=====

Powerful PHP class for working with URLs.

* Adheres as closely as possible to [RFC 3986](http://www.ietf.org/rfc/rfc3986.txt)
* Fully IPv6 ready

<pre>    foo://username:password@example.com:8042/over/there?name=ferret#nose
    \_/   \________________________________/\_________/ \_________/ \__/
     |                     |                     |           |        |
  scheme                authority               path        query   fragment</pre>

    $url = new ehough_curly_Url('foo://username:password@example.com:8042/over/there?name=ferret#nose');

    $url->getAuthority();      // username@example.com:8042
    $url->getFragment();       // nose
    $url->getHost();           // example.com
    $url->getPath();           // /over/there
    $url->getPort();           // 8042
    $url->getQuery();          // name=ferret
    $url->getQueryVariables(); // array('name' => 'ferret');
    $url->getScheme();         // foo
    $url->getUser();           // username