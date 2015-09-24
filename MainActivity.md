##AndroidStudioUberWebview 

WebView set to match dimensions of your android phone; set to uber mobile website. Great Format for setting up Web-Apps.
Language:Java
//Import Statements
```
import android.app.ActionBar;
import android.support.v7.app.ActionBarActivity;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.Menu;
import android.view.MenuItem;
import android.view.Window;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
```
//Extending AppcompatActivity style with no actionbar
```
public class MainActivity extends AppCompatActivity {
    WebView mywebView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mywebView = (WebView)(findViewById(R.id.webView));
        mywebView.setWebViewClient(new WebViewClient());
        mywebView.loadUrl(("https://m.uber.com/")); //Change url inside to link to another web-app site
        WebSettings webSettings = mywebView.getSettings();
        webSettings.setJavaScriptEnabled(true);
    }
```

//Note that I left the ability to Create the Menu inside in case

```
    @Override
    public boolean onCreateOptionsMenu(Menu menu){
        getMenuInflater().inflate(R.menu.menu_main, menu);
        return true;
    }
```
// note the onOptionsItemSelected; while the style takes away the action bar, I left the option of an menu incase
```
    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        int id  = item.getItemId();
        if(id == R.id.action_settings){
            return true;
        }
        return super.onOptionsItemSelected(item);
    }
}`
```
