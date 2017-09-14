```
import { Http, Response, Headers } from "@angular/http";
import 'rxjs/Rx';
import { Observable } from "rxjs";


this.http.post('http://localhost:3000/message', body, {headers: headers})
.map((response: Response) => {
    const result = response.json();
    const message = new Message(result.obj.content, 'Dummy', result.obj._id, null);
    this.messages.push(message);
    return message;
})
.catch((error: Response) => Observable.throw(error.json()));
```