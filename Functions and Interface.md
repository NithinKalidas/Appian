# Best Practice in Interface

## 1. What is the best practice of interface?
 *Break complex interfaces into reusable component rules (Modular Coding)
 *Use local variables to reduce recalculations and improve performance.
 *Avoid unnecessary queries inside the interface; preload data with rule inputs and Querying the data only in parent interface to reduce queries

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
Difference: Returns the values in array1 and not in array2.
Eg: difference({1, 2, 3, 4}, {3, 4}) returns 1, 2
Symmetric Difference: Returns the values from two integer arrays that are not in both arrays.
Eg: symmetricdifference({1, 2, 3, 4}, {3, 4, 5, 6}) returns an array with 1, 2, 5, 6

## 10. what is the difference between len, length and Count?
Len: Returns the length in characters of the text.
Eg: len("New York", "San Francisco"), Returns {8, 13}.
Length: This function returns the number of elements in an array.
length({10, null, 30}), Returns 2. Null values are skipped.
Count: Returns the number items in all arrays passed to the function. Null parameters are also counted.
Eg:count(1,2,3,4) returns 4

## 11. what is the difference between where and where Contains?
Where: Returns the true value of the indexesof that array.
Eg: where({68, 89, 82, 90, 93, 99, 59, 49, 88, 27, 56, 49, 100} < 50), Returns {8, 10, 12}.
WhereContains: Receives one or more values and returns an array of indexes that indicate the position of the values within the array.
Eg: wherecontains(20, {10, 20, 30}), Returns {2}.

## 12. what is the depriciated function and how do you handle objects which are utilising them?
A deprecated function (or feature) is a piece of code that is still functional but is no longer recommended for use by the developers. It is formally marked for future removal and has typically been replaced by a newer, more efficient, more secure, or more consistent alternative.
1.Create a New Version: Create a new rule with the updated, non-deprecated logic.
2.Update Precedents: Go to each object using the old rule (found via "Where Used") and change the reference to point to the new rule.
3.Deactivate the Old Rule: Once all references are updated, deactivate the deprecated rule to prevent future use.

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

## 17 . Why should the read-only grid's pagingInfo match the data's pagingInfo?
This is because the data has to be refreshed based on each page.

## 18 . Why shouldn’t an interface have more than 500 lines of code? How to reduce the number of lines of code?
More than 500 lines of code can lead to binding issues. This can be solved using modular coding.

## 19 . What is the difference between local variables and rule inputs?
Local Variables: Used when the scope is within the interface/rule and the value need not go outside that object. They are also used to define the repetitive piece of code/function/rule.
Rule Inputs: Used when the value has to be taken outside the object.



