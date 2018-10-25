# Description:
Use this step to branch the flow data down different paths according to conditions in the flow logic. 

# Help:
This step is useful in causing the flow to move in different directions according to different conditions that exist in the step data. You define certain condition(s) that, if they are met, will cause the flow to proceed down the associated exit leg on this step (“`condition exits`”). 

When the step is reached in the flow, each `condition exit` will be evaluated in order, from top to bottom (in the __step details pane__) or left to right (in the __flow diagram__). The step proceeds down the first __exit leg__ for which the associated condition is met. There is no limit on the number of `condition exits`, but the step will only ever choose one during an execution. If no conditions were met in any of the `condition exits`, the step will exit through the __else exit leg__.

## Condition exits
Every `condition exit` has two elements: the definition of the ___condition rule(s)___ that must be met for that exit to be selected, and the __exit leg__ in the step down which the flow will proceed if that condition is met. You must define at least one `condition exit`, and you can have as many `condition exits` as you need.

Clicking the `Add new exit` button creates a new `condition exit` and adds a new __exit leg__ to the step on the __flow canvas__.

Each `condition exit` consists of ___name___, ___description___, one or more ___condition rules___, and a ___match type___. When you first add the step to the canvas, it won’t have any `condition exits` already included; clicking the `add new exit` button will add one with the default ___name___ __"New Exit 1"__. Each `condition exit` is represented as a gray rectangle in the __step details pane__, and as an __exit leg__ on the step in the __flow canvas__. Note that the `condition exit` ___name___ in the __step details pane__ is the same as the label for the corresponding __exit leg__ on the step in the __flow canvas__. This ___name___ can be changed by clicking it in the __step details area__. `Condition exits` can be reordered using the __grab handle__ to the left of each rectangle, and can be deleted from the step by clicking the __X__ button in the upper-right of the rectangle. If the left edge of a `condition exit` rectangle is __red__, it means there is an error in one or more of its inputs; otherwise the left edge of the rectangle will be __green__.

The ___name___ is the label for the `condition exit` in the __step details pane__ and on the corresponding __exit leg__. This is set by default but can be manually changed. Typically, the ___name___ will be a very short description of what the `condition exit` represents, e.g., __“yes”__ vs. __“no”__, __“red”__ vs. __“blue”__ vs. __“green”__, etc.

The ___description___ of the `condition exit` is empty by default but can be manually added. This can be helpful when you need to provide a longer explanation for what that `condition exit` represents and/or when it would be selected. This field is intended to help you make your flows more readable, but it is not required and will not affect the flow execution in any way.

The ___condition rule___ is a set of conditions that must be met for a `condition exit` to be selected. A ___condition rule___ is represented by a white rectangle inside of the gray rectangle of a `condition exit` in the __step details pane__. Each `condition exit` has one ___condition rule___ by default but can have any number of ___condition rules___. You can add ___condition rules___ to the `condition exit` by clicking on ```Add rule``` button and delete ***condition rules*** by clicking on the __X__ button on the right of a ***condition rule*** rectangle.

The conditions for comparing the data of a ___condition rule___ are set with _Data type_ dropdown, _Input value_ field, _Condition_ dropdown and _Condition value_ field: 

- The _data type_ can be either _"string"_, _"number"_, _"object or array"_ or _"advanced"_. Choose _"string"_ if you want to compare textual data. Choose _"number"_ if you want to compare numerical data (use period for decimals). Choose *“object or array”* if you want to compare data that is represented in  form of an object or an array. Choose *“advanced”* if you want to compare unspecified type of data in *code mode* using JSON format. The _data type_ is represented by a blue dropdown and is set as _"string"_ by default. To change it, click on the dropdown and choose one of the given variants.

  

- The data set in *input value* and *condition value* fields  is the data that is being compared. They are represented by white rectangles inside of the ***condition rule*** rectangle, *input value* on the left, *condition value* on the right. Depending on the chosen *data type*, this data can be filled in plain text mode either manually (click inside the rectangle), with a *merge field* (click on **{x}**), or in *code mode*.

  

- You can change how the _input value_ and the _condition value_ will be compared using the dropdown between those two fields. The method of comparison depends on the type of the data being evaluated:

  

* _string (text)_

  

* _contains_: This is true if the input value exists anywhere in the condition value (e.g., "May 2007 Sales Figures" _contains_ "Sales").

  

* _doesn't contain_: This is true only if the input value cannot be found anywhere in the condition value (e.g., “Dave Jones” _doesn’t contain_ “Mr.”).

  

* _exactly matches_: This is true when the text in input and condition values match completely (e.g., "John" _exactly matches_ "John")

  

* _starts with_: This is true if the text in the condition value exactly matches the first characters in the input value (e.g., Jacksonville, FL" _starts with_ "Jack")

  

* _ends with_: This is true if the text in the condition value exactly matches the last characters in the input value (e.g., "Jacksonville, FL" _ends with_ "FL").

  

Important note: _string (text)_ values are case sensitive. You many need to use multiple conditions to handle different capitalizations, or force your input value into a certain capitalization before this step, or use JavaScript to ensure you get the right text behaviors.

  

- _number_

  

- _>_ (greater than)

  

- _<_ (less than)

  

- _>=_ (greater than or equals)

  

- _<=_ (less than or equals)

  

- _=_ (equals)

  

  

- _Vertical ellipses_ contains options for changing between _UI mode_ and _code mode_ and deleting the ___condition rule___. Note that if you switch to _Code mode_, the values previously set in _input value_ and _condition value_ fields will be lost. Use _code mode_ only if you are an advanced user.

  

  

The ___Match type___ is represented by a dropdown in the top right corner of a `condition exit` and can be either ___"any"___ or __*"all"*__. Choose __*"any"*__ if you want at least one of the ___condition rules___ be met for the flow to go through that `condition exit`. Choose ___"all"___ if you want for every ___condition rule___ be met for the flow to go through that `condition exit`.

  

  

### Advanced settings

  

___Else exit leg name___ is the label for the __Else exit leg__. It is set by default as __“else”__ but can be manually changed. The value you put in this field will show up on the __flow diagram__ above the __Else exit leg__.

  

  

The toggle ___Ignore text case___, if on, allows you to ignore upper\lower cases for the data set in _condition value_ field. Note that __Ignore text case__ toggle works only in __UI mode__ and with _"string"_ or _"any type"_ _data types_.

  

  

# Reporting Events
Default reporting event for the step is named Step. You can add additional events. Once the step has been executed, each event collects specific data, which can be used in reports. Flow composer can specify tags for each event. Tag acts as a marker for the event it is specified for. Those markers allow building more extended reports.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzg2MzM0MjMzLDEwMjA1NTg4MjJdfQ==
-->