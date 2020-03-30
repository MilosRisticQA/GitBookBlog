# Introduction to APIs

## What is an API?

An **API**, or **Application Programming Interface**, provides a way for computer systems to interact with each other. There are many types of APIs. While the types of uses for APIs are vast, the one thing all APIs have in commons is **providing functionality for use by another program**.

## Web APIs

APIs that are built with web technologies and that work in a similar way to the web are often called **web APIs** or **HTTP APIs** because, like the web, they operate over HTTP. 

## Provider and Consumer

* An API **provider** \(**server**\) is the system that provides an API for other parties to use. 
* An API **consumer** \(**client**\) is the system that uses the API to accomplish some work.

## Usage

* APIs allow sharing data between systems.
* Many modern web applications provide an API that allows developers to integrate their own code with these applications, taking advantage of the services' functionality in their own apps.

## Public and Private

* **Public APIs** are intended for consumption outside the organization that provides them.
* **Private APIs** are intended only for internal use and these APIs are subject to change at any time.

## Media Types

```text

```

* _**Media types**_ ****describe the _**format of a response's body.**_
* Media types are represented in an **HTTP** response's **`Content-Type`** header, and as a result, are sometimes referred to as _content types_.
* _**Data serialization**_ provides a common way for systems to pass data to each other, with a guarantee that each system will be able to understand the data.

  _**Types**:_ 

  * **XML** _**\(Extensible Markup Language\) -**_
  * **JSON**  _**\(JavaScript Object Notation\) -**_ can represent objects, arrays, strings, and numbers

{% tabs %}
{% tab title="XML example" %}
```markup
<address>
    <street>1600 Pennsylvania Ave NW</street>
    <city>Washington</city>
    <state>DC</state>
    <zipcode>20500</zipcode>
    <country>Unites States</country>
</address>
```
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="JSON example 1" %}
```bash
{
  "street": "1600 Pennsylvania Ave NW",
  "city": "Washington",
  "state": "DC",
  "zipcode": "20500",
  "country": "United States"
}
```
{% endtab %}

{% tab title="JSON example 2" %}
```bash
{
  "object": {
  	"city": "Boston"
  },
  "array": [1, 1, 2, 3, 5],
  "string": "Hello, World!",
  "number": 8675.309
}
```
{% endtab %}
{% endtabs %}

