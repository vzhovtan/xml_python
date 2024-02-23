# XML Parse With Python Using ElementTree: Practical Approach
XML parse with Python and parsing other data formats such as  JSON and YAML are one of the key elements to develop today's automation solution and implement complex applications using machine-to-machine communication. These formats are widely adopted amongst modern solutions such as Kubernetes and Ansible and, at the same time, are heavily utilized by a lot of hardware vendors for programmatic API.

In this tutorial you will go through the XML data format and some Python modules to work with XML files and documents. XML is one of the major data formats also known as encoding and has been recognized many times as hefty and not as readable as some other formats such as JSON and YAML. 

XML is verbose and complex to use. It is mostly used to exchange highly structured data between applications (machine-to-machine communication). 

This tutorial will help network and system automation engineers utilize the power of Python's modules to parse and process XML files. This tutorial would benefit you the most, if you have some beginner level Python experience and a basic understanding of what data format is. 

I intentionally avoided OOP to concentrate on specific topic which is parsing XML with Python.

**In this tutorial you will learn how to:**

* Explain and understand the meaning of data serialization and deserialization.
* Understand major data formats, like JSON, XML and YAML.
* Understand the main features of XML and why it is still important today.
* Compare different Python modules to **parse XML documents**.
* Get practical experience with Python XML parser to process the data.

## Introduction to Serialization and Deserialization of Data

Serialization and deserialization may sound like unfamiliar terms at first, however, you, as a person do those two things on a daily basis. 

Take for example a telephone call between two people. When you are talking to another person over the phone, your words have to transform into a series of bits that are then sent over an electronic medium or a wireless signal. Your speech has to literally transform into something understandable to the media that it is going through. This process is called serialization. 

On the other side of that telephone call, a receiver has to do the opposite process in order to extract the meaning out of the bits sent over and reconstruct your words, this process is known as deserialization.

### What Is Data Serialization and Deserialization in Computer Science

Serialization in computer science indicates converting a data structure or an object into a binary or textual format which can then be stored and reconstructed later. 

You want to save an object constructed in your code to a file, giving it permanent storage. This way, you preserve the state of said object. Serialized files could be in YAML, JSON, XML, or any other textual data format or a binary format. From now on, you'll focus on textual formats because of their convenience and wide usage.

The serialized file can now be transferred to any other system over the network. The receiving system is able to open that file and reconstruct it to the original state with all the objects defined inside. This process is the opposite of serialization and once again, is referred to as deserialization.

### How These Processes Are Used in Today's Automation and Data Exchange Applications

These two processes are not relevant only to saving and restoring files on a local computer. They are very relevant to Application Programming Interface calls.

An application programming interface (API) is a programmatic interface through which operations can be run through code or from the command line. APIs also require reliable serialization and deserialization in order to exchange data. Most programming languages, such as Python, have pre-existing tools for working with various data formats.

Here is a practical example that you could be facing as a network or automation engineer working with network programmability or, for example, server automation. 

You have written some code in Python for configuring devices in your enterprise and you want to send the data kept in your objects to the device API in a format that it will understand properly. In that case you would have to convert that Python data structure into a valid YAML, JSON, or XML format. To do that, you will use the serialization process.

In other times, you might want to get some information about a specific parameter on your device through that same API. You would receive the configuration of that device from the API in YAML, JSON, or XML format. 

To interpret that file so your Python code could understand it, you would use the deserialization process. Basically, you are extracting the details out of a textual file and converting it into valid Python objects. This process is also called data or file parsing.

### XML, JSON and YAML Data Format Comparison

There are many different data formats used for applications to communicate with a wide range of APIs available on the Internet. Each format represents syntax coding data that could be read by another machine but in a way that is easily understandable to humans as well.

For instance, if you want to use an API to configure a router in your network, you have to check which data types are supported by that API. Then, you can start writing a request to be handled by that API that has an effect on your device configuration. An API server comprehends your code and translates it into instructions that are suitable for your device to process and create an action.

You will most likely encounter these common data formats:

* eXtensible Markup Language (XML)
* JavaScript Object Notation (JSON)
* AML Ain't Markup Language (YAML)

Let's take a look at the example and compare XML, JSON and YAML formats.

The first example is XML data format:

``` xml
<user>
  <name>Some user</name>
  <location>
    <city>San Francisco</city>
    <state>CA</state>
  </location>
  <roles>Super Admin</roles>
</user>
```

Then, you can see the same information represented in JSON format:

``` json
{
   "name": "Some user",
   "location": {
      "city": "San Francisco",
      "state": "CA"
   },
   "roles": "Super Admin"
}
```

And, finally, again the same information in YAML format:

``` yaml
user:
 name: "Some user"
 location:
  city: "San Francisco"
  state: CA
 roles: "Super Admin"
```

As previously mentioned, XML has been recognized many times as not so legible to humans, contrary to the two other formats. XML is verbose, redundant, and quite complex to use. 

It is mostly used to exchange highly structured data between applications (machine-to-machine communication). When you are talking about programming in Java, XML is widely used. However, do not assume XML could be used with JAVA programming language only.

JSON is serving as an alternative to XML because it is often smaller and easier to read. It is mostly used for transmitting data between a server and a web page. 

The JSON syntax is the same as in the JavaScript programming language and therefore, you can very easily convert JSON data into JavaScript objects. 

JSON syntax is also useful for YAML, because JSON is basically a subset of YAML. Parsing JSON files with a YAML parser is therefore very intuitive.

If you are building your first API or application and you are not a developer, YAML would be a way to go with when choosing which data format to use. 

YAML is made for people who are starting to write code from scratch. XML and JSON are mostly for your programming code to be more machine readable, that is why you export YAML into one of these two formats. YAML is used in many configuration files today. Because of its similar indentation styles, YAML files are quite familiar for people that know Python. 

In general, JSON and YAML formats are widely used for configuration files and JSON in addition quite often used for REST API. XML, however, is used most of the time for machine-to-machine data exchange.

### Why XML?

Taking into account the comparison between JSON, YAML and XML you may ask why we are still talking about XML if there are two nicer and more legible formats. 

Or at least, these two are much easier to use and read for people_ and as a result, data parsing and code maintenance is easier for developers. 

In addition to that YAML and JSON are the standard languages for Kubernetes manifests and YAML is the official "native" language for Ansible automation solution. 

There is, however, some areas where XML is still playing a major role and appears to be irreplaceable.  One of the best example is YANG data model which is found on almost each and every network device and YANG data models reflect to XML documents natively. That makes XML one of best choices to learn when you are considering network automation. 

Another example, is XHTML which is the translation of HTML 4.0 into XML by W3C. W3C introduced XHTML to bridge the gap between HTML and XML, and to introduce more people to XML. 

XHTML is simply an application that mimics HTML 4.0 in such a way that you can display the results (true XML documents) in current Web browsers. So if you are thinking about Web parsing you may again consider studying XML since it is a good choice.

Microsoft's .NET initiative is substantially based on XML, which it uses to send data back and forth between .NET components. In .NET, you don't usually see the XML (it's handled behind the scenes automatically) but it's there. 

Lastly, application of XML is an offloading and reloading of database and store and arrange the data, which can customize your data handling needs. If you are working on .NET components or interested in data science, XML may be quite relevant.

## XML as Data Formats and It's Common Use Cases

XML is verbose, redundant dama format and mostly used to exchange highly structured data between applications. Let's start with reviweing XML history and common characterstics and then go to Namespaces and XPath.

### XML Brief History

The beginnings of XML go back to the 20th century, with the first version initially defined in 1998. It is very similar to HTML and they are both markup languages, meaning that they indicate which parts of a document are present and not how the data is going to be shown in your system specifically.

XML history began with the development of Standardised Generalised Markup Language (SGML) by IBM in the 1970s. SGML despite the name is not a mark-up language, but is a language used to specify mark-up languages. 

The purpose of SGML was to create a vocabulary which could be used to mark up documents with structural tags. It was imagined at the time, that certain machine readable documents would remain machine readable for perhaps decades.

One of the most popular applications of SGML came with the development of HyperText Markup Language (HTML) by Tim Berners Lee in the late 1980s. Since its development HTML was rapidly adopted and extended in many ways, beyond its original vision. It remains very popular today, though as presentation technology, and is considered unsuitable as a general purpose data storage format.

When it comes to data storage and interchange, HTML was and still is a bad idea, as it was originally intended as a presentation technology, while SGML is considered too complex for general use. XML covers this gap by being both human and machine legible, while being flexible enough to support platform and architecture independent data interchange.

### XML Common Characteristics

Since XML has been targeted as markup language its code heavily uses:

``` xml
<tags> </tags>
```

to surround elements in form as: 

``` xml
<key>value</key>
```

All the information about an object is defined inside the openings tag and closing tag with a slash. When using tags, you have to be careful that the beginning and ending tags match up both in the name itself and the same letter case. For example:

``` xml
<tag>...</TAG>
``` 

would not work properly, whereas: 

``` xml
<tag>...</tag> or <TAG>...</TAG>
```

would work correctly. Note that it is the same tag name that only differs in letter case. That said, each of the tags represent a completely different Element. Usually in XML, tag names that are all written in lower case.

Whitespaces can be quite important in certain formats or languages, however, they can also carry no significance in others. Take as an example YAML or Python and compare with JSON or JavaScript.
XML is a combination of both approaches. Significant whitespaces are a part of the document content and are always preserved. A good example is the whitespaces inside the value or opening and closing tag: 

``` xml
<t1>JohnHopkins</t1>
```

is not the same as: 

``` xml
<t1>John Hopkins</t1>
```

Whitespaces that are mostly meant to make XML documents more humanly understandable are insignificant whitespaces and are used between different tags and because of that: 

``` xml
<t1><t2>
```

is considered the same as:

``` xml
<t1>  <t2>
```

Let's take a look at the XML document example:

``` xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <name>Some user</name>
  <location>
    <city>San Francisco</city>
    <state>CA</state>
  </location>
  <roles>Super Admin</roles>
</user>
```

The document starts with the thing called XML declaration:

``` xml
<?xml version=`1.0` encoding="UTF-8"?>
```

XML declaration contains details that prepare an XML processor to parse the XML document. It is optional, but when used, it must appear in the first line of the XML document. An XML declaration should follow some rules, for example, if the XML declaration is present it has to be on the first line of the document and must contain the XML version. Interesting fact is that the XML declaration has no closing tag, so there is no such thing as:

``` xml
</?xml>
```

An object in the XML document usually contains multiple other objects inside it, as shown in the example. The main object startwith tag **user** that ends with **/user** tag with a slash at the end of an output. It is composed of many other tags such as:

``` xml
<name>`, `<location>`, `<roles>
```

to provide all the information needed about that specific user. 

An object can either contain basic information (such as a name) or more complicated data with tags nested inside that object, such as location in this case. 

Because of that XML documents are a tree-like structure that is easy to interpret by human and supports a hierarchy. With convention sections defined by a beginning and an ending tag, called elements. 

Since it is a tree-like structure we should have a root and there is one here. The largest, top-level element is called the root, which contains all other elements. It i:

``` xml
<user> </user>
```

element in the example above. And there are some attributes which are part of XML elements. An element can have multiple unique attributes. 

Attribute gives more information about XML elements. To be more exact, they define properties of elements. 

An XML attribute is always a name-value pair. Let's take a look at short example of attributes:

``` xml
<device>
   <interface type="GigabitEthernet">
   </interface>
   <interface type="Loopback">
   </interface>
</device>
```

In this example, we have categorized the interfaces by including an attribute category and assigning different values to each of the elements. Hence we have two categories of interface, one Loopback and GigabitEthernet. Therefore, there are two interface elements with different attributes.

Despite the XML being a markup language it is still a language and how can you imagine the programing language without comments. In fact, XML comments are quite similar to HTML comments and like always, they are added as notes or lines for understanding the purposes of an XML code.
They look like:

``` xml
<!--Street names are loaded from ABC source-->
```

The last attribute of the document (and not to mix it with element attribute) is encoding. In computer science encoding is the process of converting characters into their equivalent binary representation. 

When the XML parser reads an XML document, it encodes the document depending on the type of encoding. Therefore, we need to specify the type of encoding in the XML declaration. 

There are two encoding options UTF-8 and UTF-16 and the XML files encoded with UTF-8 tend to, most of the time be slightly smaller in size than those encoded with UTF-16 formats.

The XML tree structure makes navigation, modification, and removal quite simple programmatically and that is a good reason to keep reading and getting closer to practical examples. But before that you still have to go through few other important topics.

### XML Namespaces

By having an increasing number of XML files exchanged through the Internet, you can quickly come into a situation where two or more applications use the same tag names but represent a completely different object (from that tag) at the same time. 

Here, you see a conflict with systems trying to parse some information from a specific tag that uses different hierarchy then the system expects to get. Solving that issue requires the use of namespaces and prefixes:

``` xml
<table>
  <td> Car </td>
  <td> Bicycle </td>
</table>
```
  
``` xml
<table>
  <kind> Dinner table </kind>
  <material> Metal and glass </material>
</table>
```

In this example, you can see the same table element in two separate XML documents. Even though the starting tag name is the same, each element represents different information, which will later cause a name conflict. 

The upper XML code carries HTML table information, whereas the lower one carries information about a table as a furniture Element. 

You can avoid the name conflict by defining a prefix and a namespace for each of those two elements, as shown below:

``` xml
<a:table xmlns:a="namespace_URI_a">
  <a:tr>
    <a:td> Car </a:td>
    <a:td> Bicycle </a:td>
  </a:tr>
</a:table>
<b:table xmlns:b="namespace_URI_b">
  <b:tr>
    <b:kind> Dinner table </b:kind>
    <b:material> Metal and glass </b:material>
  </b:tr>
</b:table>
```

A prefix is an alphabetic character or a string put before the actual tag name followed by a colon:

``` xml
<a:tag_name> or <b:tag_name>
```

This way, you are defining an exact tag name for your application to parse correctly. When you are using prefixes in XML, you also have to define namespaces for those prefixes. 

The name of a namespace is a Uniform Resource Identifier (URI), which provides uniquely named elements and attributes in XML documents.

Namespaces are defined with the xmlns attribute in the starting tag of an element and a syntax as: 

``` xml
xmlns:prefix="URI"
```

A URI can be any string as long as they are different from any other URI. It can also be a URL linking to a specific page with a definition of that namespace. However, there is no need for the URL to be accessed. The only thing that matters is that the URI uniquely represents a logical namespace name.

### Introduction to XPath

XPath is an XML Path Language that is defined by the World Wide Web Consortium (W3C). It uses expressions to reference or extract parts of XML documents. 

It also contains several useful functions for nodes, numbers, and strings. XPath uses "path like" syntax to identify and navigate nodes in an XML document. Expressions address an XML document and return a result that can be of one of the following type categories:

* Node set: multiple elements extracted from the XML document
* String: a single string element
* Number: a single number element
* Boolean: true or false

The most common path expressions are the following:

| Expression | Description                                                                                           |
|------------|-------------------------------------------------------------------------------------------------------|
| nodename   | Selects all nodes with the name "nodename"                                                            |
| /          | Selects from the root node                                                                            |
| //         | Selects nodes in the document from the current node that match the selection no matter where they are |
| .          | Selects the current node                                                                              |
| ..         | Selects the parent of the current node                                                                |
| *          | Selects any element at a given level                                                                  |

It is always good to see the example of the complex entities because it gives much more insight about how things works under the hood. Let's follow the same practice and use the example:

``` xml
<?xml version="1.0" encoding="UTF-8" ?>
<device>
  <Loopback>
    <name>0</name>
    <ip>
      <addresses>
        <primary>
          <address>192.168.101.101</address>
          <mask>255.255.255.255</mask>
        </primary>
      </addresses>
    </ip>
  </Loopback>
  <GigabitEthernet>
    <name>1</name>
    <ip>
      <addresses>
        <primary>
          <address>172.16.10.10</address>
          <mask>255.255.255.252</mask>
        </primary>
      </addresses>
    </ip>
  </GigabitEthernet>
</device>
```

If you are not familiar with IP network addressing, do not worry about that. You are not going to deep dive in the switches and routers now, you'll just see how XPath expressions work. The following expression:

``` xml
.//primary/address
```

will give you the addresses for both interfaces:

``` console
<address>192.168.101.101</address>
<address>172.16.10.10</address>
```

However, if you would like to filter out the GigabitEthernet interface nodes and not get the Loopback IP address in the result set you should use another expression:

``` xml
.//GigabitEthernet//primary/address
```

And, this time you would see the following output:

``` console
<address>172.16.10.10</address>
```

Actually, XPath is quite a large topic and it is one that deserves its own tutorial, so I will just stop here and start closer to the more interesting part of the tutorial and you will dabble with some examples. 

But before you go there I should cover some important topics such as XML vulnerabilities and the usage of XML as a data format in the automation solutions. And I promise they are not going to be long.

### XML Vulnerabilities

Security should not be the last thing to think about. Actually, it has to be considered as a primary concern when you are planning or creating your application or solution. 

You should be aware that the XML processing modules are not secure against maliciously constructed data. An attacker can abuse XML features to carry out denial of service attacks, access local files, generate network connections to other machines, or affect the firewalls. 

Two attacks that should be noted here are SQL injection and Cross-Site Scripting. Well, these two are not related to XML only, but you can see the "XML related implementation" of such attacks. 

Another one, which is equally as infamous is  Billion Laughs Attack also known as XML Bomb attack. 

This tutorial is not dedicated to Denial of Service attacks or Web vulnerabilities, however, you have to always remember that there are some known vulnerabilities related to XML and, at least validate the XML document you are going to process.

### Using XML as Data Format in Automation Solutions

You are probably curious on how XML can be used as a data format in automation solutions. 

One of such solutions is network device programmability, for example, the majority of network hardware support NETCONF protocol. 

Network Configuration Protocol (NETCONF) is a network device configuration management protocol that provides mechanisms to install, manipulate, and delete configurations on network devices. 

It also provides a mechanism for notification subscriptions and asynchronous message delivery. NETCONF uses XML for data encapsulation before exchanging. 

You should also not forget about YANG which is a modeling language that is used with NETCONF and in an increasing number of other domains. 

YANG is used to define configuration and operational state data models, additional operational functions, and notifications that are transported within NETCONF commands. YANG is expressed in XML, that is, an instance of something that is modeled in YANG can be appearing as an XML document. 

These two examples that show how XML is a key player in network automation and if your area of interests includes networking, XML is going to be your "must-know" skill. And know how to parse XML with Python is "msu-have" knowledge.

And now, let's go to more interesting topics and learn about different Python XML parsers and play with some examples.

## Major Python Modules for XML Parsing: Features and Comparison

Python offers numerous modules for the manipulation of XML data. The main differentiation between them is the way that they parse an XML file into Python elements. 

If you are familiar with the Document Object Model (DOM), you could use the minidom module, which in turn converts an XML data into DOM objects. For an experience similar to working with YAML or JSON files, you could use xmltodict, which converts an XML document into a Python dictionary. 

Another heavily used option is the ElementTree module, which represents XML data in a hierarchical format shown in a tree structure. It is often described as a hybrid between a list and a dictionary inside Python. 

You are going to use the XML file I crafted for examples in this chapter and this one closely related to IP phone configuration to make your practical exercises closer to real life. 

I intentionally avoided using XML documents with "flowers", "cars" and anything like that to make your practices more related to a real programming task you may encounter in your career. I am not going to keep this file "frozen" and it will modify when the task requires it to. Let's start with the simplest form yet:

``` xml
<device>
   <deviceProtocol>SIP</deviceProtocol>
   <devicePool>
      <dateTimeSetting>
         <dateTemplate>M/D/YA</dateTemplate>
         <timeZone>Eastern Standard/Daylight Time</timeZone>
         <ntps>
            <ntp>
               <name>pool.ntp.org</name>
               <ntpMode>Unicast</ntpMode>
             </ntp>
         </ntps>
      </dateTimeSetting>
      <callManagerGroup>
         <members>
            <member priority="0">
               <callManager>
                  <ports>
                     <sipPort>5060</sipPort>
                     <securedSipPort>5061</securedSipPort>
                  </ports>
               </callManager>
            </member>
         </members>
      </callManagerGroup>
   </devicePool>
</device>
```

Let's start with xmltodict module.

### Xmltodict Module

xmltodict is a simple library that helps your working with XML feel like working with native Python dictionary. Under the hood xmltodict parse XML documents and create OrderedDict objects and after parsing you can call any XML element by its name. Let's see that in an example:

``` pycon
>>> import xmltodict
>>> with open(our_example_file) as file:
...     doc = xmltodict.parse(file.read())
    
>>> print(doc["device"]["deviceProtocol"])
SIP

>>> print(doc["device"]["devicePool"]["dateTimeSetting"]["timeZone"])
Eastern Standard/Daylight Time

```

As you can see loading and parsing XML file by xmltodict allows you to have native Python dict objet and then you can access elements, attributes, and values. One of the main benefits of xmltodict is speed. 

XML parsing and processing is very fast with the use of this module. The module xmltodict also supports namespaces and has a streaming mode with a small memory footprint. 

The last feature is very efficient if you need to parse a large XML file which could possibly not fit into the memory. You can install xmltodict by using:

``` console
$ python3 -m pip install xmltodict
```

### xml.minidom Module

An xml.minidom module is included into Python STL and serves as a minimal implementation of the Document Object Model interface. It was created to be simpler than the full DOM and also significantly smaller. 

The full xml.dom module is also included into STL. Let's use xml.minidom module and process the same file:

``` pycon
>>> import xml.dom.minidom
>>> with open(our_example_file) as file:
...     dom = xml.dom.minidom.parse(file)
    
>>> print(dom.firstChild.tagName)
device

>>> tz = dom.getElementsByTagName("timeZone")
>>> print(tz[0].firstChild.nodeValue)
Eastern Standard/Daylight Time
```

You can use the parse function on the XML minidom to load and parse the XML file and then have variables dom and dom get the result of the parse function. You can then print the nodename and child tagname from the file, so we declare it in print function. 

Nodename and child tagname are the standard names or properties of an XML dom (in case if you are not familiar with these type of naming conventions).

As you can see, there are some pros and cons for xml.minidom module. It is quite small and easy to use if you have experience with DOM models and familiar with nodename, tags and other fancy features of DOM. 

Otherwise, this one may not be your best choice and you may consider taking a look at lxml and ElementTree ones.

### LXML Module

Let's start by taking a look at lxml module. Well, the official name is lxml.Etree and I, personally, like this module. This is because it resonates with Python objects quite well. 

An element is the main container object for the ElementTree API. And the rest of the XML tree functionality is accessed through this particular class. The following features should sound quite harmonic to Python programmers: elements are lists, elements carry attributes as dicts, elements contain text as strings. 

I love just the sound of these features and the thought of how well and harmonically they work together. I am sure you know how to work with lists, dicts and strings in Python and that makes lxml a really great choice for you. You can also use XPath to find text and do tree iterations:

``` pycon
>>> from lxml import etree
>>> with open(our_example_file) as file:
...     tree = etree.parse(file)

>>> root = tree.getroot()
>>> print(root.tag)
device

>>> children = list(root)
>>> for child in root:
...     print(child.tag)
deviceProtocol
devicePool

>>> for child in root:
...     print(child.text)
SIP
```

### ElementTree Module

ElementTree is another module which is included in STL and it is probably one of the most widely known modules to parse XML with Python. If you use Google to search how to parse XML ElementTree, you would find it in the first 5 results. 

Let's take a look at the same file and get the same data as before, but now using this module:

``` pycon
>>> import xml.etree.ElementTree as ET
>>> tree = ET.parse(our_example_file)
>>> root = tree.getroot()
>>> root.tag
"device"

>>> for child in root:
...     print(child.tag)
deviceProtocol
devicePool

>>> root[0].text
"SIP"

>>> for item in root.findall("devicePool"):
...     for item1 in item.findall("dateTimeSetting"):
...         print(item1.find("timeZone").text)
        
Eastern Standard/Daylight Time
```

A couple of benefits provided by this are: ElementTree is included in STL, and it is quite powerful and flexible.

### Beautiful Soup

You may be asking yourself, why would I mention this module here, in this tutorial. This one is supposed to be carefully broken down and explained in the tutorial dedicated for Web Scraping and we have courses created for that. 

But don't forget  - XML is a markup language like HTML. That means if you are parsing Web pages and are searching for specific tags using Beautiful Soup you can use the same module for XML parsing. 

Of course, you can cross the river on a raft instead of ferry, but you always have such a possibility. Let's try to see what we can do with the same file using Beautiful Soup:

``` pycon
>>> from bs4 import BeautifulSoup
>>> with open(our_example_file) as file:
...     soup = BeautifulSoup(file)

>>> soup.getText()
'SIP\n\n\nM/D/YA\nEastern Standard/Daylight Time\n\n\npool.ntp.org\nUnicast...'

>>> for item in soup.find_all("timezone"):
...     print(item.text)
Eastern Standard/Daylight Time
```

As you can see the processing an XML document with Beautiful Soup is quite similar to ElementTree and other modules. Beautiful Soup transforms an HTML document into a tree of Python objects. 

But you'll only need to use Tag objects if you are going to utilize Beautiful Soup for parsing XML. Tag objects correspond to an XML or HTML tag in the original document and may be used to search a particular element in the document.

### Which One Should I Use?

Let's do a judgement call here. 

xmltodict and lxml modules are really good for Python developers. The only disadvantage is that you need to install one of them as standalone module. It is not a complex procedure and you have probably done that to many of your applications already. 

However, many developers prefer to use modules provided with Python Standard Library and we have reviewed a couple of them. Remember Batteries Included Python motto. While minidom is lightweight, ElementTree is much more powerful and easy to use for application developers not familiar with DOM model. 

Beautiful Soup could be used to parse XML with Python, but it is a much better fit for the HTML parsing. 

Because of that I will continue to use ElementTree in this tutorial for further examples. 

## XML Parse With Python Using ElementTree

Before moving to review ElementTree in details, let's create new XML examples we are going to use further. 

Since you are going to dive deeper in XML processing we have to have more complex files and it has to be a document close to real life. Otherwise, what is the point of practicing if you cannot use the gained experience later on. 

To make our interaction more colorful let's use the scenario. And don't think it is some artificial example, I have been asked once to complete the similar task myself.

Today is Monday and you start your new job as Python developer, you are responsible for automation of the entire flock of servers, network devices and who knows what else may suddenly emerge. 

You have started to get to know your team and tool set and at 10:00 AM your new boss is calling you and asking to provide him the list of IP addresses assigned to physical interfaces on all routers in building "A" network. 

It is a really scary task, you may have no idea where to find these things called routers and why your boss mentioned physical interfaces. Are there virtual one as well? And yes, you have heard about IP addresses before, but what they look like? 

You asked for help from your mentor and she mentions that you have to call around 35 devices in the entire building and each device will return you the XML file you need to process. 
The XML file looks like:

``` xml
<?xml version="1.0" encoding="UTF-8" ?>
<device>
<deviceName>Router 1</deviceName>
<interface type="Loopback">
  <name>0</name>
  <ip>
    <address>
      <primary>
        <address>192.168.101.101</address>
        <mask>255.255.255.255</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>0</name>
  <ip>
    <address>
      <primary>
        <address>172.16.10.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>1</name>
  <ip>
    <address>
      <primary>
        <address>172.16.20.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>2</name>
  <ip>
    <address>
      <primary>
        <address>172.16.30.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
</device>
```

The good thing that you already have the module which will connect to each device and return the necessary information as XML file (remember, I mentioned YANG and NETCONF before). 

That means you just have to create a Python application to combine all of that information to the results including all the device names and a list of addresses in **address** element. And yes, Loopback is virtual interface so you should not include it in the result. The result has to include GigabitEthernet interfaces only. 

Now it sounds less scary but there are still some questions. Which tools should be used? What is be the best module to use and so on... 

Unfortunately, your mentor left for some urgent meeting and you are alone with your laptop and your boss was looking for the answer yesterday. You don't have time to look around, so you have decided to go to Real Python as one of the most reliable information resources and you started searching for the immediate solution to be used for your tasks. 

You don't want to circle around looking for some fancy libraries or modules and would like to use whatever you have available on hand. You realize there is a powerful and easy module included in Python Standard Library and it is already available on your laptop, you just have to verify if it fits for your tasks.

You started analyze the provided file and see that **device** is the single root element and it contains all the other elements, such as ** interface** which are the child elements or subelements. 

Note that these child elements can also be considered as parents and contain their own child elements, which are then called "sub-child elements" and so on.

You noted that, for example, the **interface** element contain an attribute "type" that give more information. You have decided to use ElementTree module and you need to know about it's features and find out of there are limitations which could prevent you from using this one.

### ElementTree Features and Limitations in More Details

As I have already mentioned a built in library, ElementTree, has functions to parse and process XML documents. By the way, this module is able to process other similarly structured files and that makes this module very popular and powerful. You can parse XML files by reading directly from file and also you can do the same by reading from string. 

When you parse the document you crate a tree structure and define the root and more about that in following examples. Don't forget that not all elements of the XML document will become an elements in the tree. At this time, this module skips any XML comments, processing instructions and document type declarations in the file. 

Most of the parsing functions are blocking ones and that means the function requires the entire document to be read at once before returning the tree. 

However, there is non-locking API which allow  to use specific XMLParser and feed data into it incrementally. But it can be inconvenient to use for simpler use-cases because of flexibility of some parsers and if you don't mind about blocking your application while reading the file you should skip this feature for now. 

There are many methods to find an interesting element in the tree and we will cover them later on in practical example. As I said before, doing something is much better than just reading about it. You can also build and modify XML document and there are two specific practical examples are covered later. 

However, ElementTree has some limitations and may be the most important of them is XPath expression support. This module supports basic expressions, however, for more sophisticated tasks you may think about choosing another module. 

Another limitation is "pretty-printing" functionality and you will see how to deal with this limitation in oue of the practical examples.

### Validation of XML Document

Your mentor is running from one urgent meeting to another, reminding you not to forget about security and XML vulnerabilities and this remark just gave you the idea to start with the processing of the data collected. First, you should verify if the XML document is valid and correct, or in other word, you should validate XML documents.

You have decided to take this advice seriously and review your test file to be sure it is valid XML file. You know that valid XML should include a root Element. Each of the child elements has to be enclosed in its self-explanatory tags. Finally, the order of the tags is maintained. 

The XML Document Type Declaration, also known as DTD, is a way to describe XML language explicitly and precisely. An XML DTD can be either specified inside the document, or it can be kept in a separate document. 

There is one more term you should learn now and it is  XSD or XML Schema Definition. XSD declares a predefined schema for XML file. Most of the time, you may create a code to do XML file validation using XSD and it is not so hard. 

However, XML validation, XSD and DTD are very large topics themselves and should be covered separately. Just don't forget about this action in future when you start to create a production application for XML parsing in Python.

### Parse XML File Using ElementTree

As you can see in the XML document you got as an example the device name is the one of the child elements. Other child elements are interface related information such as name and address. 

However, interface's name and address are saved slightly differently. Interfaces name is the attribute while the address is one of sub-child elements. Each element has tag and may have attribute and text. 

They can addressed with the Element.tag, Element.attrib and Element.text. 

You decided to start and first of all the XML file have to be parsed in your application:

``` pycon
>>> import xml.etree.ElementTree as ET
>>> tree = ET.parse(our_example_file)
>>> root = tree.getroot()

>>> root.tag
device

>>> root.attrib
{}
```

At this point, you successfully parsed XML file and set the root element by using tree.getroot() method. As an example of element, root has a tag and a dict of attributes. 

Remember, ElementTree represents XML data in a hierarchical format shown in a tree structure and every tree has to have the root. And do not forget about common characteristics of XML elements and document structure. After you built the tree and defined the root element you can take a look at the tag assigned to root element in XML document. 

As you identified the root element's tag is "device". Itseems to be quite easy to do so while you have the XML file opened in your editor side-by-side with your Python code. It may, however, be not so easy to find tag element or some attributes for XML file you parse in your application form network or loaded from storage. 

Checking root tag and attributes helps you to identify where you should start from.

### Finding Interesting Elements in the Tree

The next step is to go over all elements in the document. ElementTree has very powerful method to do so  and it is `root.iter()`. You used list comprehension to build an element list and take a look at the result:

``` pycon
Result 1

>>> element_list = [element.tag for element in root.iter()]
>>> element_list
["device", "deviceName", "interface", "name", "ip", "address", "primary", "address", "mask", \
 "interface", "name", "ip", "address", "primary", "address", "mask", \
 "interface", "name", "ip", "address", "primary", "address", "mask", \
 "interface", "name", "ip", "address", "primary", "address", "mask"]
```

I can't even imagine any processing of XML document without using this method. This one helps iterate recursively over all the sub-tree below the element you specify. 

That is includes its children, their children, and so on.

The result 1 looks interesting. You can see there are some unique elements and some repeating ones. 

The tag "deviceName" seems to be what you should look at first. Most likely this element contains the name of the device you have to save as one of the key element in your report. Let's try to analyze this element closer. But wait...  

There is no information in the result which elements are child ones and which ones are sub-child. That should be important since we are working with tree structure. 

Let's try to dig deeper and build a structure. You will start from top-level elements or "child" element and use "for" loop:

``` pycon
Result 2

>>> for element in root:
...     print(element.tag, element.attrib, element.text)
    
deviceName {} Router 1
interface {"type": "Loopback"}
interface {"type": "GigabitEthernet"}
interface {"type": "GigabitEthernet"}
interface {"type": "GigabitEthernet"}
```

There are some interesting observations. First of all you got the list of all child elements and there is nothing about sub-child elements. 

That is expected because you were looking at elements at "root" level. Then, you got all child element tags, attributes and text data. It is clear that there is no attributes for "deviceName" element denoted as empty dict {}, but there is a text value for this Element. 

For other elements you got only attributes denoted by {'type':'GigabitEthernet'} or interface {'type': 'Loopback'} and there is no textual information. 

However, if you compare this result with the result from root.iter() method you can identify that "interface" element most likely contains some sub-child elements. 

You decided to go further and investigate one of the sub-child elements deeper. 

There are few methods provided by ElementTree module you would use very often and they are:

* Element.findall() can find only elements with a tag which are direct children of the current Element. 
* Element.find() will help to find the first child with a particular tag
* Element.text helps to access the element's text content
* Element.get() accesses the element's attributes

As you can expect Element.findall(), Element.find() and Element.get() methods allow to specify some parameters for search , while Element.text one just return  the elements text content. 

Having these tools in your toolbox you decided to find attributes and text content for all interfaces denoted as "interface" Element. But hold on here...  

You have done part of that already and have attributes for all these element in the Result 2. You take some of the information form Result 1 and keep building the application further. 

You can see that sequence "'interface', 'name', 'ip', 'address', 'primary', 'address', 'mask'" is repeated in the Result 1 few times and the number of repetitions is the same as number on interfaces in Result 2. 

You decided to poke around each interface to see  what information could be extracted:

``` pycon
Result 3

>>> for iface in root.findall("interface"):
...     for ip in iface.find("ip"):
...         for item in ip.find("primary"):
...             print(item.tag)
            
address
mask
address
mask
address
mask
address
mask
```

Comparing all results you have by now, you can identify that there is an element with tag **deviceName** without any attributes which contains device name as a text content. 

There are 4 elements with tag **interface** and their attributes contain interface's type which you can use for saving in the report or for filtering. And for each **interface** element we have hierarchy beneath and there are address and mask there. 

You decided to extract this information:

``` pycon
Result 4

>>> for iface in root.findall("interface"):
...     for ip in iface.find("ip"):
...         for item in ip.find("primary"):
...             print(item.tag, item.text)
            
address 192.168.101.101
mask 255.255.255.255
address 172.16.10.10
mask 255.255.255.252
address 172.16.20.10
mask 255.255.255.252
address 172.16.30.10
mask 255.255.255.252
```

All looks good now and then next step you are doing is building the complete output which will be saved later in the overall result:

``` pycon
Result 5

>>> for device_name in root.findall("deviceName"):
...     print(device_name.text)
    
Router 1

>>> for iface in root.findall("interface"):
...     print(iface.attrib)
...     for ip in iface.find("ip"):
...         for item in ip.find("primary"):
...             print(item.tag, item.text)
            
{"type": "Loopback"}
address 192.168.101.101
mask 255.255.255.255
{"type": "GigabitEthernet"}
address 172.16.10.10
mask 255.255.255.252
{"type": "GigabitEthernet"}
address 172.16.20.10
mask 255.255.255.252
{"type": "GigabitEthernet"}
address 172.16.30.10
mask 255.255.255.252
```

This approach works, but does this one looks elegant? I do not think so and you very likely agree with me. 

If you are looking for the way to get all child elements and the information is mostly contained in element's attributes and text in them then these methods are good enough. 

However, if the XML document is highly hierarchical as in this example, these regular methods may not be so useful and XPath expressions are coming to rescue. But before looking at them you should review one more very helpful method which can help to reveal a lot of details in the document. 

This method is Element.tostring and actually each element has a Element.tostring() method. If you pass the root into the Element.tostring() method, you can return the whole document.

Do not forget that XML document support the encoding and, since ElementTree is a module that can parse and process more than just XML, you should specify both the encoding and decoding of the document you are going to display as the string:

``` pycon
Result 6

>>> print(ET.tostring(root, encoding="utf8'").decode("utf8"))
<?xml version="1.0" encoding="utf8"?>
<device>
<deviceName>Router 1</deviceName>
<interface type="Loopback">
  <name>0</name>
  <ip>
    <address>
      <primary>
        <address>192.168.101.101</address>
        <mask>255.255.255.255</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>0</name>
  <ip>
    <address>
      <primary>
        <address>172.16.10.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>1</name>
  <ip>
    <address>
      <primary>
        <address>172.16.20.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
<interface type="GigabitEthernet">
  <name>2</name>
  <ip>
    <address>
      <primary>
        <address>172.16.30.10</address>
        <mask>255.255.255.252</mask>
      </primary>
    </address>
  </ip>
</interface>
</device>
```

As you can see, even if you have no idea about structure and content of XML document you can reveal this "hidden" information by using Element.tostring() method and then build your code to extract the necessary information. 

Before going to cover Xpath expression and how to use them for your task there is one tips for you. Try to use both Element.find() and Element.findall() methods and see the difference in results. 

You may be surprised how one small change in used method can change the result and, hence, the code's behavior. 

There is one more additional note. You may recall what I have said about importance of root.iter() method. Let's see how to capture the interfaces's addresses much easier:

``` pycon
Result 7

>>> for ipaddr in root.iter("address"):
...     print(ipaddr.text)
    
192.168.101.101
172.16.10.10
172.16.20.10
172.16.30.10
```

### Exploring XML Trees With XPath Expressions

You should be quite good now because you are able to get the data from all devices and parse them with ElementTree module in your Python application and save all data in the report. But there is one concern here.

The request was to include only physical interfaces information and not virtual. As you know by now Loopback interface is virtual and has to be excluded from the report. 

Or course, it is possible to do that with some filtering in the code by checking interface element attribute and excluding unnecessary details. 

However, there is more Pythonic way to do that. Recall, from the "Introduction to XPath" section that XPath is an XML Path Language which uses expressions to reference or extract parts of XML documents. 

Let's leverage power of XPath to create more elegant code and include only the data which have been requested to be in the report:


``` pycon
Result 8

>>> for iface in root.findall(".//interface[@type='GigabitEthernet']"):
...     print(iface.attrib)
...     for ipaddr in iface.findall(".//primary/address"):
...         print(ipaddr.text)

{"type": "GigabitEthernet"}
172.16.10.10
{"type": "GigabitEthernet"}
172.16.20.10
{"type": "GigabitEthernet"}
172.16.30.10
```

There you are. You uses XPath expression to filter only GigabitEthernet interfaces by selecting appropriate attribute and then going down from selected node by using ".//" notation. 

You have presented your report to your mentor and suddenly realized that you can't make a difference between all interfaces on the same device. All of them are GigabitEthernet type, but you can't see the names. Let's make a small change to the code and have better result:

``` pycon
Result 9

>>> for iface in root.findall(".//interface[@type='GigabitEthernet']"):
...     print(iface.attrib)
...     for name in iface.findall(".//name"):
...         print(name.text)
...     for ipaddr in iface.findall(".//primary/address"):
...         print(ipaddr.text)

{"type": "GigabitEthernet"}
0
172.16.10.10
{"type": "GigabitEthernet"}
1
172.16.20.10
{"type": "GigabitEthernet"}
2
172.16.30.10
```

You can apply other expressions, but remember that ElementTree provides limited support for XPath. Well, now everything looks clear and you can finalize your report. You have created final code and presented it to your mentor:

``` pyton
import xml.etree.ElementTree as ET

tree = ET.parse("XML_file_from_device")
root = tree.getroot()

report = {}
interface_data = {}

dev_name = root.find("deviceName").text

for iface in root.findall(".//interface[@type='GigabitEthernet']"):
    #Selecting only GigabitEthernet interfaces
    for name in iface.findall(".//name"):
        iface_name = name.text
    for ipaddr in iface.findall(".//primary/address"):
        iface_address = ipaddr.text
    interface_data[iface_name] = iface_address

report[dev_name] = interface_data
print(report)
```

When you run this code against you test XML file you got the proper result:

``` console
{"Router 1": {"0": "172.16.10.10", "1": "172.16.20.10", "2": "172.16.30.10"}}
```

There are still ways to modify the code to apply some formatting and so on and you decided to do that later, after you got the first report is done. 

However, there is one more thing you should take care about before running your code in production. You have been told that XML files which are coming from some devices contain namespaces. 

Hence, there is no other way, but modify your code again to support namespaces. If you have some experience with networking you should ask me why I have not include subnet mask into the report. 

The answer is quite easy - I would like to make examples more readable and including a subnet mask information will just add unnecessary visual noise. And, in real, life you should of course find and add subnet mask to the report.

### How to Utilize XML Namespaces With ElementTree

You took a look at the XML files which you have received form these sophisticated devices and such files looks like:

``` xml
<?xml version="1.0" encoding="UTF-8" ?>
<device>
<deviceName>Router 1</deviceName>
<a:interface type="Loopback" xmlns:a="http://192.268.0.1/virtual">
  <a:name>0</a:name>
  <a:ip>
    <a:address>
      <a:primary>
        <a:address>192.168.101.101</a:address>
        <a:mask>255.255.255.255</a:mask>
      </a:primary>
    </a:address>
  </a:ip>
</a:interface>
<b:interface type="GigabitEthernet" xmlns:b="http://192.168.0.1/physical">
  <b:name>0</b:name>
  <b:ip>
    <b:address>
      <b:primary>
        <b:address>172.16.10.10</b:address>
        <b:mask>255.255.255.252</b:mask>
      </b:primary>
    </b:address>
  </b:ip>
</b:interface>
</device>
```

Hence, you should adjust your code to take care about namespaces and search for necessary elements. 

One way to explore such XML file is to manually add the URI to every tag or attribute in the xpath of an Element.find() or Element.findall(). I assume, you have not forgotten what is the URI by now, otherwise you can go back and re-read "XML Namespaces" chapter:

``` pycon
>>> import xml.etree.ElementTree as ET
>>> tree = ET.parse(XML_file_with_namespaces)
>>> root = tree.getroot()

>>> for iface in root.iter("{http://192.168.0.1/physical}interface"):
...     print(iface.attrib)
{"type": "GigabitEthernet"}

>>> for iface in root.iter("{http://192.268.0.1/virtual}interface"):
...     print(iface.attrib)
{"type": "Loopback"}
```

However, there is much more elegant way to do that. You can create a dictionary with your prefixes and then use them in the search functions: 

``` pycon
>>> namespace = {"physical": "http://192.168.0.1/physical", "virtual": "http://192.268.0.1/virtual"}

>>> for iface in root.findall("physical:interface", namespace):
...     print(iface.attrib)
{'type': 'GigabitEthernet'}

>>> for iface in root.findall("virtual:interface", namespace):
...     print(iface.attrib)
{'type': 'Loopback'}
```

As you can see having namespaces in XML file is not big deal and you can handle them quite easy. At this point of time your code is ready and you start to run it in production. 

It is running smoothly and gathering the requested data from all devices and saving it in Python dictionary. That should be sufficient and you think your task is completed. 

However, just before you pick up the phone to let your boss that you are done for the day, new e-mail popped up, requesting to save all captured data  in XML file. 

Or to be more precise, new information has to be added to existing XML inventory file. You have no other choice, but to keep exploring the XML and ElementTree and move to the next section. 
     
### Practical Example of Updating XML Document: Adding New Element

You have the Python dict object which contains the data from the device produced by your code. And this object in the report looks like:

``` console
Generated report

{"BldgAFl1RTR1": {"0": "172.16.11.10", "1": "172.16.21.10", "2": "172.16.31.10"},\
    "BldgAFl1RTR3": {"0": "172.16.70.10", "1": "172.16.80.10", "2": "172.16.90.10"}}
```          

You connect to the server where existing inventory file located and review files' structure:

``` xml
Inventory file

<?xml version="1.0" encoding="UTF-8" ?>
<devices>
  <device>
    <deviceName>BldgAFl1RTR1</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.10.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.20.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.30.10</address>
      </interface>
    </interfaces>
  </device>
  <device>
    <deviceName>BldgAFl1RTR2</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.40.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.50.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.60.10</address>
      </interface>
    </interfaces>
  </device>
</devices>
```

This one looks like regular XML file and it seems you just need to append your report to the file. However, after careful consideration, the process may be not so easy. 

What if there are existing data in the inventory file for the same device you collected report for? There is a collision in this case and the information in the inventory XML file has to be updated instead of just appending. That means you have to parse XML with Python again and add some code to handle collision and inventory file modification.

First, you should learn couple more new things. ElementTree is good for parsing XML file and processing them. However, if you prefer to keep the same pretty format for the output you will need to some additional tricks. Let's see in example what does that mean for you.

You created the simple code to check if there is a collision or you should just append new data to the inventory file:

``` python
import xml.etree.ElementTree as ET

tree = ET.parse(inventory_file)
root = tree.getroot()

inventory_devices = []
for device in root.iter("deviceName'"):
    inventory_devices.append(device.text)

for report_device in report.keys():
    if report_device in inventory_devices:
        print("Collision, update may be needed for", report_device)
        update_the inventory()
    else:
        print("Append has to be done for", report_device)
        append_to_inventory()
```

Function "update_the inventory()" and "append_to_inventory()" are empty now and you will create them later.
When you run this code you got the following output:

``` console
Collision, update may be needed for BldgAFl1RTR1
Append has to be done for BldgAFl1RTR3
```

Everything looks good now and the result is expected as you can find by doing manual review of the inventory file and generated report.
You decide to move on and create "append_to_inventory()" function first. To do that you can use Element.append() method. 

You may create a new element by utilizing element() method. ONce the new element is created you can modify it directly by changing its fields, Element.text for example. You can also add and modify element's attributes with Element.set() method. Let's see how it works:

``` python
def append_to_inventory(report, device_name, tree):
    """
    Create new element for the new device with all attributes, adding it to the tree and saving new tree as a file
    """
    root = tree.getroot()
    new_device = ET.Element("device")
    new_name = ET.SubElement(new_device, "deviceName")
    new_name.text = device_name
    new_interface_list = ET.SubElement(new_device, "interfaces")
    for int_name, int_address in report[device_name].items():
        new_interface = ET.SubElement(new_interface_list, "interface", attrib={"type": "GigabitEthernet"})
        new_name = ET.SubElement(new_interface, "name")
        new_name.text = int_name
        new_address = ET.SubElement(new_interface, "address")
        new_address.text = int_address

    ET.dump(new_device)
```

There is one ElementTree function which I like a lot and it is .dump() one. You should not use it in production, but it is great for debugging purposes. When you add the "append_to_inventory()" function to your code and run the it you get:

``` console
Collision, update may be needed for BldgAFl1RTR1
Append has to be done for BldgAFl1RTR3
<device><deviceName>BldgAFl1RTR3</deviceName><interfaces><interface type="GigabitEthernet"><name>0</name><address>172.16.70.10</address></interface><interface type="GigabitEthernet"><name>1</name><address>172.16.80.10</address></interface><interface type="GigabitEthernet"><name>2</name><address>172.16.90.10</address></interface></interfaces></device>
```

That is interesting. First couple lines are expected, but 3rd line doesn't look like the XML document. Actually, it is XML element create by your function. 

Why it looks differently then? That is because ElementTree does not do any “pretty printing”. And if you will add this element to the tree and then save it in the file you will have the same valid XML element, but it may be not good for human to read. 

There is one trick you can apply. To make the output easier for human readers, you can re-parse the XML with xml.dom.minidom then use its toprettyxml() method. Here is the function you can use to make the element more "readable":

``` python
def make_pretty_print(element):
    """
    Return a pretty-printed XML string for the Element.
    """
    original_string = ET.tostring(element, "utf-8")
    new_string = minidom.parseString(original_string)
    return new_string.toprettyxml(indent="  ")
```

You decided to be not so strict about using ElementTree only since xml.dom.minidom module is also included in Python Standard Library and available for you. You modified "append_to_inventory()" function and use Element.append() method and ElementTree.write() method. 

The entire "append_to_inventory()" function looks like:

``` python
def append_to_inventory(report, device_name, tree):
    """
    Create new element for the new device with all attributes, adding it to the tree and saving new tree as a file
    """
    root = tree.getroot()
    new_device = ET.Element("device")
    new_name = ET.SubElement(new_device, "deviceName")
    new_name.text = device_name
    new_interface_list = ET.SubElement(new_device, "interfaces")
    for int_name, int_address in report[device_name].items():
        new_interface = ET.SubElement(new_interface_list, "interface", attrib={"type": "GigabitEthernet"})
        new_name = ET.SubElement(new_interface, "name")
        new_name.text = int_name
        new_address = ET.SubElement(new_interface, "address")
        new_address.text = int_address

    new_device_pretty = make_pretty_print(new_device)
    new_element = ET.fromstring(new_device_pretty)
    root.append(new_element)
    tree.write("new_inventory.xml", encoding="utf-8", xml_declaration=True)
```

You run your code and "new_inventory.xml" file looks good now:

``` xml
New inventory file

<?xml version='1.0' encoding='utf-8'?>
<devices>
  <device>
    <deviceName>BldgAFl1RTR1</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.10.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.20.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.30.10</address>
      </interface>
    </interfaces>
  </device>
  <device>
    <deviceName>BldgAFl1RTR2</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.40.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.50.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.60.10</address>
      </interface>
    </interfaces>
  </device>
  <device>
    <deviceName>BldgAFl1RTR3</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.70.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.80.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.90.10</address>
      </interface>
    </interfaces>
  </device>
</devices>
```

NOTE: I specifically saved the data in a new file. It may be a good practice to save the result in a new file, then parse it again and do some tests, for example, verify the number of devices in the new file and check if device names are correct. After verification, you can replace the old file with the new one. I will leave this step for you as a homework assignment.

You have implement the half of changes and now starting to code the "update_the inventory()" function. 

### Practical Example of Updating XML Document: Updating Element Attributes

The not so good thing is for this sub-task you have to consider what are the difference between element existing in inventory file and element in new report. 

If you will not do that, every time you run the code you will get new report and you will be overwriting the inventory file. 

However, if you would skip this step altogether you may end up having outdated information in the inventory file. First thing first you decide to create function to compare element's attributes in inventory file and in report.

NOTE: We make one assumption that "deviceName" is constant and will not change. Otherwise, you would need to find another unique attribute which will be expected to stay constant. 

We also make assumption the number of interfaces on the device is not changing as well.

The function to compare such attributes you created looks like:

``` python
def attribute_compare(report, device_name, root):
    for device in root.findall("device"):
        if device.find("deviceName").text == device_name:
            for iface in device.findall(".//interfaces/interface"):
                iface_name = iface.find(".//name").text
                iface_addr = iface.find(".//address").text
                if report[device_name][iface_name] != iface_addr:
                    return True
    return False
```

You are using XPath expressions again to make code simpler. When you run this function it returns "True" as expected, because the interface addresses in inventory file and in report are different and device "BldgAFl1RTR1" has to be updated. 

There are two ways actually to update the element in XML document. You can do that by removing old element with Element.remove() method, create new element from the report as you did in "append_to_inventory()" function and append it to the inventory file. The second approach is to use either Element.set() method or change the filed directly as I mentioned before. 

You have decide to use the second approach  and, since you know that information in the report is up-to-date
you created the "update_the inventory()" function to change address element directly. The new code looks like:

``` python
import xml.etree.ElementTree as ET
from xml.dom import minidom

def make_pretty_print(element):
    """
    Return a pretty-printed XML string for the Element.
    """
    original_string = ET.tostring(element, "utf-8")
    new_string = minidom.parseString(original_string)
    return new_string.toprettyxml(indent="  ")


def append_to_inventory(report, device_name, tree):
    """
    Create new element for the new device with all attributes, adding it to the tree and saving new tree as a file
    """
    root = tree.getroot()
    new_device = ET.Element("device")
    new_name = ET.SubElement(new_device, "deviceName")
    new_name.text = device_name
    new_interface_list = ET.SubElement(new_device, "interfaces")
    for int_name, int_address in report[device_name].items():
        new_interface = ET.SubElement(new_interface_list, "interface", attrib={"type": "GigabitEthernet"})
        new_name = ET.SubElement(new_interface, "name")
        new_name.text = int_name
        new_address = ET.SubElement(new_interface, "address")
        new_address.text = int_address

    # ET.dump(new_device)
    new_device_pretty = make_pretty_print(new_device)
    new_element = ET.fromstring(new_device_pretty)
    root.append(new_element)
    tree.write("updated_inventory.xml", encoding="utf-8", xml_declaration=True)


def attribute_compare(report, device_name, tree):
    """
    Comparing interface name and address for specific device and return True if there is a diff.
    Return False otherwise
    """
    root = tree.getroot()
    for device in root.findall("device"):
        if device.find("deviceName").text == device_name:
            for iface in device.findall(".//interfaces/interface"):
                iface_name = iface.find(".//name").text
                iface_addr = iface.find(".//address").text
                if report[device_name][iface_name] != iface_addr:
                    return True
    return False


def update_the_inventory(report, device_name, tree):
    """
    Update the inventory file by directly updating interface address.
    """
    root = tree.getroot()
    for device in root.findall("device"):
        if device.find("deviceName").text == device_name:
            for iface in device.findall(".//interfaces/interface"):
                iface_name = iface.find(".//name").text
                iface_addr = iface.find(".//address")
                iface_addr.text = report[device_name][iface_name]

    tree.write("updated_inventory.xml", encoding="utf-8", xml_declaration=True)


def update_inventory_with_report(report, tree):
    root = tree.getroot()
    inventory_devices = []
    for device in root.iter("deviceName"):
        inventory_devices.append(device.text)

    for report_device in report.keys():
        if report_device in inventory_devices:
            print("Collision, update may be needed for", report_device)
            if attribute_compare(report, report_device, tree):
                print("Updating the inventory")
                update_the_inventory(report, report_device, tree)
            else:
                print("Update is not needed, inventory file is up-to-date")

        else:
            print("Append has to be done for", report_device)
            append_to_inventory(report, report_device, tree)


if __name__ == "__main__":
    report = {"BldgAFl1RTR1": {"0": "172.16.11.10", "1": "172.16.21.10", "2": "172.16.31.10"},
              "BldgAFl1RTR3": {"0": "172.16.70.10", "1": "172.16.80.10", "2": "172.16.90.10"}}

    tree = ET.parse(inventory_file)
    update_inventory_with_report(report, tree)
```

When you run this code against inventory file you got the following result:

``` console
Collision, update may be needed for BldgAFl1RTR1
Updating the inventory
Append has to be done for BldgAFl1RTR3
```

The new inventory file is created and looks good:

``` xml
<?xml version='1.0' encoding='utf-8'?>
<devices>
  <device>
    <deviceName>BldgAFl1RTR1</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.11.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.21.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.31.10</address>
      </interface>
    </interfaces>
  </device>
  <device>
    <deviceName>BldgAFl1RTR2</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.40.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.50.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.60.10</address>
      </interface>
    </interfaces>
  </device>
  <device>
    <deviceName>BldgAFl1RTR3</deviceName>
    <interfaces>
      <interface type="GigabitEthernet">
        <name>0</name>
        <address>172.16.70.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>1</name>
        <address>172.16.80.10</address>
      </interface>
      <interface type="GigabitEthernet">
        <name>2</name>
        <address>172.16.90.10</address>
      </interface>
    </interfaces>
  </device>
</devices>
```

Congratulation. You have completed the task and collected the requested information from all devices, parse the XML data with Python and updated the XMl inventory file. You should have enough experience now to use XML parsing with Python in other projects.

## Conclusion

In this tutorial you explored how to parse XML with Python. 

You learned about XML as data format, compare XML with other data formats, such as JSON and YAML, learned about data serialization and de-serialization processes. 

You have got knowledge about different features of XML and available Python module to parse XML documents. 

You went through the series of exercises to gain practical experience with parsing, processing and updating XML document using ElementTree module. In this tutorial you learned how to:

* Explain the meaning of data serialization and deserialization.
* Describe the main features of XML and why it is still important today.
* Compare different Python modules to parse XML documents.
* Parse XML document with Python ElementTree module
* Process XML document and find interesting elements
* Use XPath expression for more sophisticated element search
* Modify and update existing XML document
