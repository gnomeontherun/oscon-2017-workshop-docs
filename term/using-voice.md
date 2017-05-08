# Using voice to change the term

The last little enhancement is to use the webspeech API to capture audio and use that to set the term.

Open up `src/app/term/term.component.ts` and replace it with the following. We've only added a few snippets but they are mixed throughout.

```typescript
import { Component, OnInit } from '@angular/core';

import { TermService } from '../services/term.service';

declare const webkitSpeechRecognition: any;

@Component({
  selector: 'app-term',
  templateUrl: './term.component.html',
  styleUrls: ['./term.component.css'],
  providers: [ TermService ]
})
export class TermComponent implements OnInit {
  private recognizer = new webkitSpeechRecognition();
  term: string = '';

  constructor(private termService: TermService) {}

  ngOnInit() {
    this.recognizer.onresult = (event) => {
      let transcript = '';
      for (let i = event.resultIndex; i < event.results.length; i++) {
        transcript += event.results[i][0].transcript;
      }

      this.term = transcript;
      this.changeTerm();
     };

     this.getTerm();
  }

  private getTerm() {
    this.termService.getTerm().subscribe(response => {
      this.term = response.json().term;
    });
  }

  private changeTerm() {
    this.termService.setTerm(this.term).subscribe(response => {
      this.term = response.json().term;
    });
  }

  onKeyUp(event) {
    if (event.keyCode.toString() === '13') {
      this.changeTerm();
    }
  }

  startTalking() {
    this.recognizer.start();
  }
}
```

## Start to talk button

Now we want to add a button that will start the speech recognition flow. This will call the `startTalking()` method you see in the controller.

Open up `src/app/term/term.component.html` and add the button you see here.

```html
<form class="search">
  <label for="term">
    <input id="term" name="term" type="text" placeholder="Provide term to profile" [(ngModel)]="term" (keyup)="onKeyUp($event)">
  </label>
  <button class="btn btn-primary" (click)="startTalking()">Talk</button>
</form>
```

The `webkitSpeechRecognition` API will prompt for access to the microphone when it is first used, so if you have previously denied the microphone access it might not work. You can check your settings to clear that setting. Otherwise, when it prompts you need to agree.

It works by listening for a few moments, and automatically ending when it stops hearing speaking.

![Using voice](using-voice.md)