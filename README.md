# Adult Search Aggregation
[![Build Status](https://travis-ci.org/corycollier/adult-api.svg?branch=master)](https://travis-ci.org/corycollier/adult-api)
> This project aims to allow for a simple way to query multiple "Tube" type adult sites with a simple api

The project uses the GuzzleHttp\Promise library to make multiple concurrent requests to different providers, and aggregates them into a single response.

## Usage
```php
<?php

require dirname(__FILE__) . '/../vendor/autoload.php';

use Adult\Aggregator\SearchReactor as SearchReactor;
use Adult\Provider\ServiceFactory as ServiceFactory;

$factory = new ServiceFactory;
$reactor = new SearchReactor($factory);
$results = $reactor->search('blonde');

print_r($results);
```
