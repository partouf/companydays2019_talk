<div class="slidetext-bg">

### Webbed IDL Interop

* github.com/partouf/idl_interop
* Write interface in IDL <!-- .element: class="fragment" -->

<div class="fragment">

```cpp
module test {
    interface IMyTest {
        void DoSet(string value);
        string DoGet(integer something);
    };
};
```

</div>

* Generate interfaces <!-- .element: class="fragment" -->
* Generate DLL import/exports <!-- .element: class="fragment" -->
* Generate class <!-- .element: class="fragment" -->
* Generate all the things <!-- .element: class="fragment" -->

</div>