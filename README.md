cURL-Multi PHP Wrapper Class
==============



Examples:  
```php
// create new handles
$chm = new CURL;
$chm->new_handle("http://api.example.com", [CURLOPT_POST => true]);

$response = $chm->exec();


// insert existing handles
$ch = curl_init("http://example.com");
      curl_setopt($ch, CURLOPT_RETURNTRANSFER, false);
      
$chm = new CURL;
$chm->add_handle($ch);
$chm->new_handle("http://api2.example.com");

$response = $chm->exec();


// remove handles
$chm = new CURL;
$chm->new_handle("http://api.example.com", [CURLOPT_POST => true]);
$chm->new_handle("http://api2.example.com");
$chm->new_handle("http://api3.example.com");
$chm->new_handle("http://api4.example.com");
$chm->new_handle("http://api5.example.com");

$chm->remove_handle(2); // 2nd handle added
$chm->remove_handle("http://api4.example.com"); // handle by URL

$response = $chm->exec();


// easily get information about transfers
$chm = new CURL;
$chm->new_handle("http://api6.example.com");

$response = $chm->exec();
$info = $chm->info;
```
