#Usage
webservice for CRUD  vtiger 6.x 
webservice example crud 
setup your project file by incude WSClient.php to you prject file 

## create new object
```php
$client = new Vtiger_WSClient('localhost/yourvtiger/webservice.php'); // create  webservice
$login = $client->doLogin($usernamevt,$accesskey); call login function 
```

## How to create record by webservice 
```php
$module = 'Leads';
$record = $client->doCreate($module, Array( // webservice create record 
 'firstname'=>'worawut', //create firstname
 'lastname'=>'wattana')); //create lastname
```
## How to create update by webservice
```php
$modulenumber = '10'; //// vtiger table `vtiger_ws_entity` my leads module number(id) is 10
$recordnumber = '10' // it will show at url myrecordnumber is 10 
$record = $modulenumber.'x'.$recordnumber; 
  $myrecord = $client->doRetrieve($record);
  $update = array(
    'firstname'=>'jimmy', // update firstname to jimmy
    'lastname'=>'jimmy' //  update lastname to jimmy
      );
    foreach($update as $key => $value){
	   $myrecord[$key] = $value;
        }
        $updaterecord = $client->doUpdate('Leads',$myrecord);
 ```
 
 ## How to delete record by webservice
 
 ```php
$modulenumber = '10'; // vtiger table `vtiger_ws_entity` my leads module number(id) is 10
$recordnumber = '10' // it will show at url myrecordnumber is 10 
$record = $modulenumber.'x'.$recordnumber;
$update = $client->doDelete($record);
```

