# Best Practice in Interface

## 1. What is the best practice of interface?
Break complex interfaces into reusable component rules (Modular Coding)
Use local variables to reduce recalculations and improve performance.
Avoid unnecessary queries inside the interface; preload data with rule inputs and Querying the data only in parent interface to reduce queries
Use paginated grids for large datasets to optimize load time.
Follow proper naming conventions for rules, inputs, and variables.
Ensure security with role-based visibility and record-level controls.
Test UI responsiveness across web and mobile devices. hving default test cases
Don't Hardcode: Never type specific IDs or text labels directly in the code. Use Constants so you can change them easily later without breaking the code.

## 2. What is modular coding?
Modular coding is the practice of breaking a large, complex program into smaller, independent, and manageable pieces called modules

## 3. Issues you came across in Interface and how do you resolve them?

## 4. What is the difference between a!save vs Save!value?
a!save(): In interface saveInto parameters, a!save() updates the target with the given value. This function has no effect when called outside of a component's saveInto parameter.
save!value: Holds the user inputted value on a temporary basis.

## 5. What is the difference between choice Label vs choice Value?
Choice Value: The underlying data value that gets stored when a user makes a selection.
Choice Label: The display text that the user sees in the interface.

## 6. What are the different ways to refresh a local variable?
Local variables can be refreshed in the following ways:

refreshAlways: When true, the value of this local variable will be refreshed after each user interaction and each interval refresh.

refreshInterval: How often the variable value gets refreshed in minutes. When null, the variable will not be refreshed on an interval. Valid values include 0.5, 1, 2, 3, 4, 5, 10, 30, 60.

refreshOnReferencedVarChange: When true, the value of this local variable will be refreshed each time the value of any variable it references within the value parameter is updated. Default is true.
refreshOnVarChange: Refreshes the value of the local variable each time any of these specific variables change. This allows you to refresh the value when a variable that is not referenced within the value parameter is updated.
refreshAfter: Refreshes the value of the local variable after a record action, such as a related action or a record list action configured within a record type, completes from a dialog window within the Record Action Component. Instead of requiring the entire page to reload, this parameter allows you to refresh a local variable value on an interface after a record action completes. Valid values include RECORD_ACTION.

## 8. what is the difference between a!match and display value?

## 9. what is the difference between difference and Symmetric Difference?

## 10. what is the difference between len, length and Count?

## 11. what is the difference between where and where Contains?

## 12. what is the depriciated function and how do you handle objects which are utilising them?

## 13. 2. What is an environmental constant?
The env constant is used to store values specific to the environment. For example, we can have a constant called IS_PROD whose value will be true only in the production environment. The value of the env constant can be provided in the customization file during deployment.

## 14. Can array type constants be used for comparison of values?
No. This is because if the index of the values changes, the comparison can collapse.

## 15. What is the difference between validation and validation group?
Validation: Validation errors are displayed below the field when the value does not meet certain business conditions.
Validation Group: Fields are validated only when a button in the same validation group is clicked.

## 16.##  . Scenario: Interface to fill vehicle insurance details. There is a master field to capture the type of vehicle (Car/Bike etc.), and there are sets of fields that differ for the type of vehicle selected.
Hide the sequential fields and display only the set of fields that correspond to the selected vehicle type.
Display all the fields but keep them disabled. Enable only the set of fields that correspond to the selected vehicle type.
Answer: Hide the sequential fields and display only the set of fields that correspond to the selected vehicle type.

##  . Why should the read-only grid's pagingInfo match the data's pagingInfo?
This is because the data has to be refreshed based on each page.

##  . Why shouldn’t an interface have more than 500 lines of code? How to reduce the number of lines of code?
More than 500 lines of code can lead to binding issues. This can be solved using modular coding.

##  . What is the difference between local variables and rule inputs?
Local Variables: Used when the scope is within the interface/rule and the value need not go outside that object. They are also used to define the repetitive piece of code/function/rule.
Rule Inputs: Used when the value has to be taken outside the object.

INTEGRATION
##  . When should Web API, Integration/Web service be used?
Web API: Should be used when Appian's data is to be exposed to the external system.
Integration/Web Service: Used when external system's data is consumed by Appian.

##  . When to use Web service and Integration?
Integration: Used when the data returned by the external system is in REST structure.
Web Service: Used when the data returned by the external system is in SOAP structure.

##  . What is connected systems?
Connected Systems is an object to store the connection credentials used in integrations when connecting to an external system.


## 17.

## 18.

## 19.

## 20.

## 21.

## 22.

## 23.

## 24.

## 25.

## 26.

## 27.

## 28.

## 29.

## 30.

## 31.

## 32.

## 33.

## 34.

## 35.

## 36.

## 37.

## 38.

## 39.

## 40.

## 41.

## 42.

## 43.

## 44.

## 45.

## 46.

## 47.

## 48.

## 49.

## 50.
