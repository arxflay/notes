XML DTD is a **schema**, that describes content of an xml file (what elements should xml contain, what attributes and element). Similar to RelaxNG or XSD
## Integration 

XML DTD is specified inside via `<!DOCTYPE >` inside xml, content can be inline (in document) or external (loaded from file)

1. inline
```dtd
<!DOCTYPE root_element_name [
…
]>
```
2. external
```dtd
<!DOCTYPE root_element_name RESOURCE_LOCATOR PATH_TO_SCHEME>
```
## Specification of element types

Type of value inside element is described via
`<!ELEMENT element_name type>`

where type can be one of:
1. `ANY`: element can contain any element
2. `EMPTY`: element must be empty (should not contain value)
3. `(#PCDATA)`: element contains only parsable character data - text markup symbols like '>'
4. `(element)`: sequence of elements, that contains element names. 
	Occurrences can be specified:
	1. `(element+)`: one or multiple occurences 
	2. `(element*)`: zero or multiple occurences
	3. `(element?)`: zero or one occurrence
Element can have multiple sequence type, each sequence must be separated via '|'
```
(a|b|(d, c)) - contains either a or b or d and c
```
Additionally, it's possible to mix types by adding '\*' at the end
```
(a, EMPTY)* - has either tag a or empty
```

Example of element:
```dtd
<!ELEMENT root (a, b)>
<!ELEMENT a (#PCDATA | (d, c?)*>
<!ELEMENT d (j)>
<!ELEMENT c (j+)>
<!ELEMENT j (EMPTY | #PCDATA)*>
<!ELEMENT b ANY>
```
root should contain a and b
a should contain text or elements d and c, where c is optional.
d should contain j
c should contain one or multiple j
j should be empty or contain text
b can have anything inside it

## Specification of element values

Single attribute for element is described via
`<ATTLIST element attribute_name type necessity>`

where type can be one of:
1. `CDATA`: nonparsable character data (because markup symbols inside quotes will be treated as text)
2. `(A | B | ...)`: Enumeration, e.g only A or B are allowed
3. `ID`: value must unique, document can't contain multiple element of type ID with same value
4. `IDREF`: value must be same as value of attribute of type ID from any element
5. `IDREFS`: similar to IDREF, except can have multiple ids, separated via blank space
6. `NMToken`: 
7. `NMTokens`: similar to NMToken
8. `Entity` :
9. `Entities`:
10. `Notation`:
11. `xml:`:

Necessity:
1. some_value - value, that is used if attribute doesn't exists
2. `#REQUIRED` - attribute is required
3. `#IMPLIED` - attribute is optional
4. `#FIXED` value - attribute can have only one value, for example `#FIXED "10"`

Example

## Specification of entities

It's possible to define custom entities
Entities could be defined inside DTD schema (inline, in document or dtd file) or loaded from external dtd (which can be include from another dtd)
1. inline
```xml
<!ENTITY name "value">
```
2. external
```xml
<!ENTITY name RESOURCE_LOCATOR PATH_TO_SCHEME>
```
external parameters are same as for external parameters of document



