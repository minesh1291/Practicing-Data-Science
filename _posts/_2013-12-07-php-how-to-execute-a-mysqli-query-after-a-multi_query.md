---
layout: post
title:  "[PHP] How to execute a MySQLi query after a multi_query (for PHP > 5.3) ?"
date:   2013-12-07
banner_image: PHP.jpg
tags: [MySQL, PHP]
---

I just got a problem today : I needed to execute a `$mysqli->query()` after a `$mysqli->multi_query()` and it didn’t work. Here is the error I got :

    Fatal error: Call to a member function fetch_array() on a non-object in [...]

<!--more-->

I then checked the [PHP Documentation](http://www.ivangabriele.com/wp-content/uploads/2013/12/mysqli.multi-query.php) about mysqli::multi_query and tried to use the solution suggested by [jcn50](http://www.ivangabriele.com/wp-content/uploads/2013/12/mysqli.multi-query.php#102837) but I got this error :

    Strict Standards: mysqli::next_result(): There is no next result set. Please, call mysqli_more_results()/mysqli::more_results() to check whether to call this function/method in [...]

Because it only works for PHP <= 5.2.

So I found this quite logical solution :

```php
$mysqli->multi_query("Many MySQL queries concatenated by a semicolon");

while ($mysqli->next_result()) // flush multi_queries
{
  if (!$mysqli->more_results()) break;
}

$mysqli->query("MySQL statement #1");
$mysqli->query("MySQL statement #2");
$mysqli->query("MySQL statement #3");
```
