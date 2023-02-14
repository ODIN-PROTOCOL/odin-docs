---
sidebar_position: 2
---

# Introduction to Scripts

Scripts are used to retrieve data by consumers. Since very often for obtaining
information, consumers choose several possible resources in terms of increasing the
level of objectivity. For example, suppose you want to get information about the price
of a certain asset. In that case, it is better to receive information from a certain
number of exchanges since if you receive information from only one, it can
manipulate data and send you invalid data.

Scripts allow you to define a set of data sources from which information will be
received, as well as how the received information will be processed. That is, a kind of
script is smart contracts that contain logic for operating with data sources and the
data itself.

That is, in fact, you can split the script into two logical components:

* A **set of data feeds**, data from which you want to get.
* A **data processing algorithm**.

A new script can be added to the platform with an existing account. Thus, everyone
can offer their own script for use by other contributors