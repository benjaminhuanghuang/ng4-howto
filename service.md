Create service
```    
    @Injectable()
    export class MessageService {

    }
```

Inject service into component
In this sample, MessageListComponent has a MessageService instance
```
import { MessageService } from "./message.service";

@Component({
    providers: [MessageService]
})
export class MessageListComponent implements OnInit {
    messages: Message[];

    constructor(private messageService: MessageService) {}

    ngOnInit() {
        this.messages = this.messageService.getMessages();
    }
}
```
To pass data from one component to other component, service instance should be shared between components

Solution 1:
Inject service to the parent component, all child component can share it.

Solution 2:
Inject service to the app module.

