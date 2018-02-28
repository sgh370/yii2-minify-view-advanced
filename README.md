Yii 2 Minify View Advanced Component
===========================

advanced concatenate and compress files for Yii2

Support
-------
[GutHub issues](https://github.com/sgh370/yii2-minify-view-advanced/issues).

Installation
------------

The preferred way to install this extension is through [composer](https://getcomposer.org/).

Either run

```bash
composer require sgh370/yii2-minify-view-advanced
```

or add

```
"sgh370/yii2-minify-view-advanced": "^1.15",
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
			'class' => '\rmrevin\yii\minify\View',
			'enableMinify' => YII_DEBUG,
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
			'excludeModules' => [
				'categories' => [], // all controllers of this module
				'posts' => ['index'] // exclude only index controller from posts module
			],
			'excludeUrls' => [
				'posts/add' // exclude posts/add/* (exclude url that starts with posts/add)
			],
			'excludeFiles' => [
				'jquery.js', // exclude this file from minification
				'app-[^.].js', // you may use regexp
			],
			'excludeBundles' => [
				\dev\helloworld\AssetBundle::class, // exclude this bundle from minification
			],
		]
	]
];
```

Creator: sgh370@yahoo.com
