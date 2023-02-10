# How to set up DBeaver Community Edition (on MacOS) to use the Apache Arrow Flight SQL JDBC Driver

## Here are the steps:   

1. Download DBeaver Community Edition if you haven't already - [here](https://dbeaver.io)  


2. Download the Apache Arrow Flight SQL JDBC driver - [here](https://search.maven.org/search?q=a:flight-sql-jdbc-driver) - choose the "jar" option.     


3. Launch DBeaver  


4. In the DBeaver application menu bar, open the "Database" menu and choose: "Driver Manager":      
![Driver manager menu option](images/dbeaver_database_driver_manager_menu_option.png?raw=true "Driver manager menu option")   


5. Click the "New" button on the right:     
![Driver manager new button](images/driver_manager_new_button.png?raw=true "Driver manager new button")   


6. Add the JDBC jar file:  
   1. Click the "Libraries" tab  
   1. Click the: "Add File" button   
   1. Choose the "flight-sql-jdbc-driver-11.0.0.jar" jar file - and click "Open"   
   ![Select jar file](images/select_driver_jar_file.png?raw=true "Select jar file")   
   1. Close the Driver editor window with the blue "OK" button on the lower-right   


7. Enter the driver settings:   
   1. Click the "Settings" tab   
   1. In the "Driver Name" field - enter: ```Apache Arrow Flight SQL```   
   1. In the "URL Template" field - enter: ```jdbc:arrow-flight-sql://localhost:31337?useEncryption=true&disableCertificateVerification=true```   
   1. In the "Driver Type" drop-down box - choose: "SQLite"   
   1. Your driver manager "Edit Driver" window should look like this:   
   ![Driver Manager completed](images/driver_manager_completed_window.png?raw=true "Driver Manager completed")   
   1. Click the blue "OK" button on the lower-right to save the driver   
   1. Close the "Driver Manager" window by clicking the blue "Close" button on the lower-right.

   
8. Create a new Database Connection:   
   1. In the DBeaver application menu bar, open the "Database" menu and choose: "New Database Connection":   
   ![New Database Connection](images/new_database_connection_menu_option.png?raw=true "New Database Connection")   
   1. In the "Connect to a database" window - type: ```Flight``` in the search bar   
   1. Choose the ```Apache Arrow Flight SQL``` driver - your window should look like this:   
   ![Connect to a database window](images/database_selection_window.png?raw=true "Connect to a database window")   
   1. Click the blue "Next >" button on the bottom of the window
   1. On the next screen, the JDBC URL should be filled out already - just put in the "Username" and "Password" values for your running Flight SQL server.   
   1. Click the "Test Connection" button - your window should look like this:   
   ![Test Connection results](images/test_connection_button_results.png?raw=true "Test Connection results")   
   1. Close out the "Connection Test" window with "OK", and then click: "Finish"   


9. Run a query:
   1. Right-click on the Database Connection on the left - choose: "SQL Editor", and then: "Open SQL Console" as shown here:   
   ![Open SQL Console](images/open_sql_console.png?raw=true "Open SQL Console")   
   1. In the Console window - run a query - something like: ```SELECT * FROM customer;```   
   1. Click the triangle button to execute the SQL statement - as shown below (or use keyboard shortcut: Ctrl+Enter):      
   ![Execute SQL](images/triangle_execute_button.png?raw=true "Execute SQL")   
   1. You should see the query results as shown in this screenshot:   
   ![Query Results](images/query_results.png?raw=true "Query Results")   


## Congrats - you are all done!
