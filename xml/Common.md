XML begins with `<?xml version="1.0" encoding="utf-8"?>`, version 

**XML Namespace**: Namespace is in attribute with syntax `xmlns:user_defined_prefix` (where user_defined_prefix is chosen by user), which defines prefix. It's value is URI to information about namespace, which is not parsed by parser. All children of the element, where namespace is defined, can use prefix. 
**XML Prefix**: Prevents name conflict (same tags, different meaning and content). Prefix is added before tag name and is separated via ':' (`<d:tag></d:tag>`)
qualified namespace: prefix is added

```xml
<?xml version="1.0" encoding="utf-8">
<root xmlns:prefix="URI">
	<prefix:some_tag></prefix:some_tag>
	<b></b>
</root>
```

Prefix in **XML Namespace** could be omitted, in that case, it's treated like default namespace. It's still useful, because URI will help us differentiate different elements with same name
```xml
<?xml version="1.0" encoding="utf-8">
<root xmlns:prefix="URI">
	<prefix:some_tag></prefix:some_tag>
	<b></b>
</root>
```

Entities: alias for text, which begins with ampersand and ends with semicolon, &gt - '>'. Used for characters that can't be represented in markup language via standard way.

`<!CDATA[[content]]>` - special element, where content inside this tag is parsed as text.
```xml
<root>
	<![CDATA[<a attr="value"><b>test<b></a>]]>
</root>
```
is equivalent to
```xml
<root>
	"<a attr\"value\"><b>test<b></a>"
</root>
```