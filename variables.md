# Working with Variables in Postman

## Declaring Variables
Variables in Postman are defined within a scope, and several levels are available. For this tutorial we will be using the Collection scope. To edit variables for the collection, first select your collection, and then select the Variables tab.

![Variable Tab](https://raw.githubusercontent.com/220808-Java-React-Enterprise/postman/main/images/variable_tab.png)
<br/><br/>
In the "VARIABLE" column, enter a name for the variable.  Do not type &lt;Enter&gt; unless you want a new line in the cell. Optionally enter an initial value for the variable. Be sure to place a checkmark next to any variables you want active, especially if you're defining the variable multiple times. We'll use the following definitions going forward.

![Variables](https://raw.githubusercontent.com/220808-Java-React-Enterprise/postman/main/images/variables.png)
<br/><br/>

After adding your variables, you need to click the save icon in the upper right, or the standard OS shortcut for saving. (eg CTRL+S on Windows)

NB: Saving the collection for the first time may cause the list of variables to disappear. They are still in the collection and restarting Postman should allow future edits and saving to work correctly.

## Using variables
Variables may be used in any place that accepts text. They are specified by surrounding them with a double curly brackets like this: ``{{url}}`` The following image shows ``url`` being used in the URL path, and ``authkey`` being used as the value for an ``Authorization`` header key. Other useful places are as the value of a parameter or in the body of a request.
![Getting Variables](https://raw.githubusercontent.com/220808-Java-React-Enterprise/main/postman/images/get.png)

## Saving Variables
To automatically save a variable when a request is run we will use the tests tab. The following code first takes a variable from the header ``Authorization`` and stores it in a local variable ``value``. It then sets an environment variable named ``authkey`` with the value.
![Setting Variables](https://raw.githubusercontent.com/220808-Java-React-Enterprise/main/postman/images/set.png)
```renderscript
var value = pm.response.headers.get("Authorization");
pm.environment.set("authkey", value);
```

## Further Information
More information on using variables and scripts may be found at the following pages of Postman's website.
<https://learning.postman.com/docs/sending-requests/variables/><br/>
<https://learning.postman.com/docs/writing-scripts/intro-to-scripts/><br/>
