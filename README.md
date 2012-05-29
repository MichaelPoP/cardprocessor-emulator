Cardprocessor Emulator
======================

This is a light-weight emulator of what could be a card processor. It's designed to aid in development of a card processor API recieving end.

## Setup
If you're running PHP 5.4 or greater, you can simply type in the terminal `./server`

Currently the SQL setup file is not available.

## Accessing Data
You can access data in either an XML or JSON format (default to JSON). Requests are in the format of:

`localhost:3000/Company?format=xml&username=..&password=..`

Note that you will have to specify your username/password each time when making an API call.

### Companies
To create a new company:

`/Company/new?username=username&password=password&name=CompanyName`

Which will return the ID of the company that was created.

To view company data:

`/Company?username=..&password=..`

### Persons
A person is somebody who has a card and can make transactions.

#### Attributes:
* first_name
* last_name
* address
* address_1
* city
* state (two-leter code)
* zipcode
* phone
* ssn

No attributes are required


#### Actions

To view all people for the current company:

`Person?username...`

To make a new person:

`/Person/new?username..&password=..&attribute=value&attribute2=value`

To view a specific person:

`Person/view?personId=thePersonId`

### Cards
To issue a card for a specific person. Returns card number, expiration date, etc.

#### Attributes
* status
* number
* expiration
* balance

To issue a card:

`Person/issueCard?personId=thePersonId`

To view cards for a person:

`Person/cards?personId=thePersonId`

