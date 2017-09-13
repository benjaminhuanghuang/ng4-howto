```
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from "./app.component";

@NgModule({
    // Tell angular what my app consists of
    declarations: [
        AppComponent
    ],
    // What I am going to use in my app
    imports: [BrowserModule],
    // Which is the root component
    bootstrap: [AppComponent]
})
export class AppModule {

}
```