Yii 2 Minify View Component
===========================

The main feature of this component - concatenate and compress files 
connected through "AssetBundle".

[![License](https://poser.pugx.org/hepru/yii2-minify-view2/license.svg)](https://packagist.org/packages/hepru/yii2-minify-view2)
[![Latest Stable Version](https://poser.pugx.org/hepru/yii2-minify-view2/v/stable.svg)](https://packagist.org/packages/hepru/yii2-minify-view2)
[![Latest Unstable Version](https://poser.pugx.org/hepru/yii2-minify-view2/v/unstable.svg)](https://packagist.org/packages/hepru/yii2-minify-view2)
[![Total Downloads](https://poser.pugx.org/hepru/yii2-minify-view2/downloads.svg)](https://packagist.org/packages/hepru/yii2-minify-view2)

Code Status
-----------
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/hepru/yii2-minify-view2/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/hepru/yii2-minify-view2/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/hepru/yii2-minify-view2/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/hepru/yii2-minify-view2/?branch=master)
[![Travis CI Build Status](https://travis-ci.org/hepru/yii2-minify-view2.svg)](https://travis-ci.org/hepru/yii2-minify-view2)
[![Dependency Status](https://www.versioneye.com/user/projects/54119b4b9e1622a6510000e1/badge.svg)](https://www.versioneye.com/user/projects/54119b4b9e1622a6510000e1)

Support
-------
[GutHub issues](https://github.com/hepru/yii2-minify-view2/issues) or [public chat](https://gitter.im/hepru/support).

Installation
------------

The preferred way to install this extension is through [composer](https://getcomposer.org/).

Either run

```bash
composer require hepru/yii2-minify-view2
```

or add

```
"hepru/yii2-minify-view2": "^1.0",
```

to the `require` section of your `composer.json` file.

Configure
---------
```php
<?php

return [
	// ...
	'components' => [
		// ...
		'view' => [
			'class' => '\hepru\yii\minify\View',
			'enableMinify' => !YII_DEBUG,
			'concatCss' => true, // concatenate css
			'minifyCss' => true, // minificate css
			'concatJs' => true, // concatenate js
			'minifyJs' => true, // minificate js
			'minifyOutput' => true, // minificate result html page
			'webPath' => '@web', // path alias to web base
			'basePath' => '@webroot', // path alias to web base
			'minifyPath' => '@webroot/minify', // path alias to save minify result
			'jsPosition' => [ \yii\web\View::POS_END ], // positions of js files to be minified
			'forceCharset' => 'UTF-8', // charset forcibly assign, otherwise will use all of the files found charset
			'expandImports' => true, // whether to change @import on content
			'compressOptions' => ['extra' => true], // options for compress
			'excludeFiles' => [
            	'jquery.js', // exclude this file from minification
            	'app-[^.].js', // you may use regexp
            ],
            'excludeBundles' => [
            	\app\helloworld\AssetBundle::class, // exclude this bundle from minification
            ],
		]
	]
];
```
