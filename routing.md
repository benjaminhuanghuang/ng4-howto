Config the routes

```
import { Routes, RouterModule } from "@angular/router";

import { MessagesComponent } from "./messages/messages.component";
import { AuthenticationComponent } from "./auth/authentication.component";
import { AUTH_ROUTES } from "./auth/auth.routes";

const APP_ROUTES: Routes = [
    { path: '', redirectTo: '/messages', pathMatch: 'full' },
    { path: 'messages', component: MessagesComponent },
    { path: 'auth', component: AuthenticationComponent, children: AUTH_ROUTES }
];

export const routing = RouterModule.forRoot(APP_ROUTES);
```

In app.module.ts, import routing
```
import { routing } from "./app.routing";

@NgModule({
    declarations: [
        HeaderComponent
    ],
    imports: [BrowserModule, FormsModule, routing],
    bootstrap: [AppComponent]
})
export class AppModule {

}
```
Using router-outlet in app.component.html
```
<div class="container">
    <app-header></app-header>
    <hr>
    <router-outlet></router-outlet>
</div>
```

Using routerLink to create html link in menu or header component.
When link is selected, apply 'active' style to it.
```
  <li routerLinkActive="active"><a [routerLink]="['/messages']">Messenger</a></li>                  
```

## Children Routes

```
import { AUTH_ROUTES } from "./auth/auth.routes";

const APP_ROUTES: Routes = [
    { path: '', redirectTo: '/messages', pathMatch: 'full' },
    { path: 'messages', component: MessagesComponent },
    { path: 'auth', component: AuthenticationComponent, children: AUTH_ROUTES }
];

```