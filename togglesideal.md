<div class="slidetext-bg">

### Turn up the jam

<img src="images/newtoggle.png" alt="Image of feature toggle enabled" align="middle" />

<div class="fragment">

```pascal
class procedure TfrmMain.Printscreen;
begin
  if Unleash.IsEnabled('cis.fastreportprintscreen') then
    FastReportPrintscreen
  else
    OldBrokenPrintscreen;
end;
```

</div>

</div>
