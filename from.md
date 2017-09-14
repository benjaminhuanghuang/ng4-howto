Template
```
  <div class="col-md-8 col-md-offset-2">
      <form (ngSubmit)="onSubmit(f)" #f="ngForm">
          <div class="form-group">
              <label for="content">Content</label>
              <input type="text" id="content" class="form-control"
                      ngMode name="content" required>
          </div>
          <button class="btn btn-primary" type="submit">Save</button>
      </form>
  </div>
```

Class
```
  import { NgForm } from "@angular/forms";

  onSubmit(form: NgForm) {
    const message = new Message(form.value.content, 'Max');
    this.messageService.addMessage(message);
    form.resetForm();
  }
```

Class
```
import { FormGroup, FormControl, Validators } from "@angular/forms";

export class SignupComponent implements OnInit {
  myForm: FormGroup;

  onSubmit() {
    console.log(this.myForm);
    this.myForm.reset();
  }

  ngOnInit() {
    this.myForm = new FormGroup({
      firstName: new FormControl(null, Validators.required),
      lastName: new FormControl(null, Validators.required),
      email: new FormControl(null, [
        Validators.required,
        Validators.pattern(
          "[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?"
        )
      ]),
      password: new FormControl(null, Validators.required)
    });
  }
```

Template
```
<form [formGroup]="myForm" (ngSubmit)="onSubmit()">
```