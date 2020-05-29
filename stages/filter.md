# Filter

This is the default first step in a pipeline. The basic component in a Filter is called a _condition_. By using a combination of _conditions_,  you can instruct the Filter to only process the data that matches your conditions. Let's look at an example:

Find me all the Livepeer LPT token transactions that have happened before 2/1/2020 and were initiated by the address 0x92039843. \[SCREENSHOT\]

{% hint style="info" %}
A simple token transaction can be identified by two things: a log called "transfer" and a log address. In this case, we look for the "transfer" log and the log address "0xxx" which is the smart contract address of Livepeer Token.
{% endhint %}

You could also group different _conditions_ together to achieve a more complicated filter. For example, let's try to find all the active Aragon organizations \(including new organizations\) in January or March. 

\[SCREENSHOT\]

{% hint style="info" %}
A group can be created by choosing "xxx" option.
{% endhint %}



