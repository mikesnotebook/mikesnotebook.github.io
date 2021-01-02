---
layout: page
title: "Apply user-friendly value replacements"
permalink: /da-100/replace/
---

This is easy: Replace values. This is one of the easiest commands to use and understand, so make sure you’re 100% comfortable with this. Make sure you’ve also expanded the advanced options section and are comfortable with everything here. Also make sure you know how to work with null and blank values. 
And remember, the entire point of Power Query is to make it as easy as possible to work with the data later (while still keeping the model performing well). Users do not want to see a bit field with values of 0 and 1 and have to figure out what each one means, so use this to address that. 

But this tool comes up in another scenario as well: cleaning up data before doing data type conversions. Consider the following, which is pretty common in sources like Excel files:

| Amount       |
| :------------- |
|  10 |
| 3   |
| N/A |
| 11  |

You can’t make the above a numeric data type, as the N/A isn’t numeric. So use the Replace Values to change it to a zero (or whichever value is appropriate in that context), and then do the data type conversion.