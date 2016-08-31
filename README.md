# StringEditor.cs
StringEditor

```cs
var input = ":z hello :world bye :world bye :z";
var se = new StringEditor(input);

se.Replace(":world", "bye:z");
se.Replace("bye", "BYE");
se.Replace(":z", "QQQWERQWEREr");
Console.WriteLine(se.Commit());
// QQQWERQWEREr hello bye:z BYE bye:z BYE QQQWERQWEREr


var sb = new StringBuilder(input);
sb.Replace(":world", "bye:z");
sb.Replace("bye", "BYE");
sb.Replace(":z", "QQQWERQWEREr");
Console.WriteLine(sb.ToString());
//QQQWERQWEREr hello BYEQQQWERQWEREr BYE BYEQQQWERQWEREr BYE QQQWERQWEREr
```
