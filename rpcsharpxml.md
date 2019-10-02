<div class="slidetext-bg">

### Serializable

* github.com/partouf/XmlInterop
* using System.Xml.Serialization

```c#
public class MyData {
    public string MyFirstValue { get; set; }
    public int MySecondValue { get; set; }
    public bool MyThirdValue { get; set; }
}
```

```c#
MyData data = new MyData { MyFirstValue = "hello", MySecondValue = 12, MyThirdValue = true };
XmlInterop.WriteXml(fw, data);
```

```c#
MyData data2 = XmlInterop.CreateFromXml<MyData>(xmldata);
```

</div>
