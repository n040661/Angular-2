## Component Communication <span style='float:right;font-size:12px;line-height:40px;'>4/23/2017 8:58:19 AM </span>

>**Input**

	@Component({
        selector: 'bank-account',
        template: `
          Bank Name: {{bankName}}
          Account Id: {{id}}
        `
      })
      class BankAccount {
        @Input() bankName: string;
        @Input('account-id') id: string;
     
        // this property is not bound, and won't be automatically updated by Angular
        normalizedBankName: string;
      }
     
      @Component({
        selector: 'app',
        template: `
          <bank-account bank-name="RBC" account-id="4747"></bank-account>
        `
      })
     
      class App {}

>**Output**

	@Directive({
        selector: 'interval-dir',
      })
      class IntervalDir {
        @Output() everySecond = new EventEmitter();
        @Output('everyFiveSeconds') five5Secs = new EventEmitter();
     
        constructor() {
          setInterval(() => this.everySecond.emit("event"), 1000);
          setInterval(() => this.five5Secs.emit("event"), 5000);
        }
      }
     
      @Component({
        selector: 'app',
        template: `
          <interval-dir (everySecond)="everySecond()" (everyFiveSeconds)="everyFiveSeconds()">
          </interval-dir>
        `
      })
      class App {
        everySecond() { console.log('second'); }
        everyFiveSeconds() { console.log('five seconds'); }
      }

>**HostBinding**

	@Directive({selector: '[ngModel]'})
      class NgModelStatus {
        constructor(public control:NgModel) {}
        @HostBinding('class.valid') get valid() { return this.control.valid; }
        @HostBinding('class.invalid') get invalid() { return this.control.invalid; }
      }
     
      @Component({
        selector: 'app',
        template: `<input [(ngModel)]="prop">`,
      })
      class App {
        prop;
      }

>**HostListener**

	@Directive({selector: 'button[counting]'})
      class CountClicks {
        numberOfClicks = 0;
     
        @HostListener('click', ['$event.target'])
        onClick(btn) {
          console.log('button', btn, 'number of clicks:', this.numberOfClicks++);
        }
      }
     
      @Component({
        selector: 'app',
        template: '<button counting>Increment</button>',
      })
      class App {}