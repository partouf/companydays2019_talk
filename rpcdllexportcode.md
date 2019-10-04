<div class="slidetext-bg">

### Just DLL it

<div class="fragment">

```c#
namespace csharpdll {
    public class Main {
        public static MyNewWindow frm = null;

        [DllExport(CallingConvention = CallingConvention.StdCall)]
        public static Int32 ShowSharpMesssage(
            [MarshalAs(UnmanagedType.LPWStr)] string Text
        ) {
            frm = new MyNewWindow();
            frm.DoSomething(Text);
            return frm.ShowDialog() == true ? 1 : 0;
        }
}}
```

</div>

<div class="fragment">

```pascal
function ShowSharpMesssage(const Text: PChar): Int32; stdcall; external 'csharpdll.dll';
```
</div>

</div>
