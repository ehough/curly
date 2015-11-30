## curly

[![Build Status](https://secure.travis-ci.org/ehough/curly.png)](http://travis-ci.org/ehough/curly)
[![Project Status: Unsupported - The project has reached a stable, usable state but the author(s) have ceased all work on it. A new maintainer may be desired.](http://www.repostatus.org/badges/latest/unsupported.svg)](http://www.repostatus.org/#unsupported)
[![Latest Stable Version](https://poser.pugx.org/ehough/curly/v/stable)](https://packagist.org/packages/ehough/curly)
[![License](https://poser.pugx.org/ehough/curly/license)](https://packagist.org/packages/ehough/curly)

**This library is no longer maintained.** Powerful class for working with URLs. Requires PHP 5.2+.

* Adheres as closely as possible to [RFC 3986](http://www.ietf.org/rfc/rfc3986.txt)
* Fully IPv6 ready

<pre>    foo://username:password@example.com:8042/over/there?name=ferret#nose
    \_/   \________________________________/\_________/ \_________/ \__/
     |                     |                     |           |        |
  scheme                authority               path        query   fragment</pre>

### Sample Usage

```php
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

$url->setFragment('ear');
$url->setHost('ehough.com');
$url->setPath('/paved/walkway');
$url->setPort(99);
$url->setQueryVariables(array('moon' => 'rise', 'sun' => 'set'));
$url->setScheme('teleport');
$url->setUser('melissa:salsa');

echo $url->toString(); // teleport://melissa:salsa@ehough.com:99/paved/walkway?moon=rise&sun=set#ear
```