<div class="slidetext-bg">

### WM_ - Wild Messages

```pascal
procedure OpenDotNetWindow;
begin
  var Handle := FindWindow(nil, 'DelphiListener');
  SendMessage(Handle, WM_USER + 1, 0, 0);
end;
```

```c#
public partial class DelphiListener : Window {
    private static DelphiListener __instance;
    private HwndSource source = null;

    public DelphiListener() {
        InitializeComponent();
        __instance = this;
    }

    public static DelphiListener GetInstance() {
        if (__instance == null)
            new DelphiListener();
        return __instance;
    }

    private void Window_Activated(object sender, EventArgs e) {
        if (source == null) {
            source = HwndSource.FromHwnd(new WindowInteropHelper(this).Handle);
            source.AddHook(new HwndSourceHook(WndProc));

            ShowInTaskbar = false;
            Visibility = Visibility.Hidden;
        }
    }

    private static IntPtr WndProc(IntPtr hwnd, int msg, IntPtr wParam, IntPtr lParam, ref bool handled) {
        const int WM_USER = 0x400;

        if (msg == WM_USER + 1) {
            var Win = new MainWindow();
            Win.Owner = DelphiListener.GetInstance();
            Win.Show();
            Win.Activate();
        }

        return IntPtr.Zero;
    }
}
```

</div>
