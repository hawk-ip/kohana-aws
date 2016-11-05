Kohana AWS
=============

Kohana wrapper module for the Amazon AWS PHP SDK.

1. [Installation](#installation)
1. [Usage](#usage)

## Installation

#### Install the module

Replace xyz in the following with the Github author for your fork of this module.

```
git submodule add git@github.com:xyz/kohana-aws.git modules/kohana-aws
git submodule update --init --recursive
```

#### Load dependencies

Ensure Composer is available for your PHP project.

Install the AWS SDK by running `composer require` from your project's root directory.

```
composer require aws/aws-sdk-php
```

#### Configuration

Edit `application/bootstrap.php` and add this module:

```
Kohana::modules(array(
    ...
    'aws' => 'modules/kohana-aws',
    ...
));
```

Copy `modules/kohana-aws/config/aws.php` to `APPPATH/config/aws.php` and setup your config.

## Usage

```php
<?php

class Controller_Amazon extends Controller {

	public function action_index()
	{
		// List some S3 buckets
		$s3 = Amazon::instance()->get('s3');

		// Execute an S3 method
		$result = $s3->listBuckets();

		// Do something with it here
	}
}
?>
```

#### Full AWS SDK Usage

http://docs.aws.amazon.com/aws-sdk-php/latest/
