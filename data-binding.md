## Two binding property
```
  <input type="text" [(ngModel)]="message.content">
```

## Property binding
```  
  [property]="expression"
```
  Can be used to DOM properties(value, hidden), Directive properties(ngStyle) or Component properties.

Class
```
  import { Component, Input } from "@angular/core";

  export class MessageComponent {
      @Input() message: Message;

  }
```
Template
```
  <app-message [message]=""></app-message>
```

## Event binding
```
  (event)="expression"
```
  Can be used to DOM evens(click, mouseover), Directive events or Component events.

Class
```
  import { Output, EventEmitter } from "@angular/core";
  
  @Output() editClicked = new EventEmitter<string>();

  onEdit() {
        this.editClicked.emit('A new value');
    }
```

Template
```
     <a (click)="onEdit()">Edit</a>
```
Parent component
```
  <app-message [message]="message" (editClicked)=""></app-message>
```
