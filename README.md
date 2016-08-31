# StringEditor.cs
StringEditor<br>
<br>
__StringBuilder__ : 모든 변경작업이 즉시 수행됩니다. 매번 `Replace`를 호출할 때 마다 이전 작업에 영향을 받습니다.<br>
__StringEditor__ : 변경작업이 버퍼에 저장되고, `Commit`이 호출된 시점에 모두 적용됩니다. `Replace`는 항상 마지막 `Commit` 혹은 생성 시점의 문자열을 바라보고 작업됩니다.

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
