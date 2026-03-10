
---

# 1️⃣ `app.component.html`

Write your **HTML form here**.

```html
<h2>Registration Form</h2>

<form>

  Name:
  <input type="text"
         [(ngModel)]="name"
         (input)="checkName()"
         name="name"
         required>

  <br>

  Email:
  <input type="email"
         [(ngModel)]="email"
         name="email"
         required>

  <br><br>

  <button type="button" (click)="submitForm()">
    Submit
  </button>

</form>

<br>

<div [ngClass]="messageClass" *ngIf="message">
  {{message}}
</div>
```

---

# 2️⃣ `app.component.ts`

Write the **logic here**.

```typescript
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { CommonModule } from '@angular/common';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [FormsModule, CommonModule],
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {

  name: string = '';
  email: string = '';
  message: string = '';
  messageClass: string = '';

  checkName() {

    if (this.name && this.name.length < 3) {
      this.message = "Name must be at least 3 characters";
      this.messageClass = "error";
    } else {
      this.message = "";
    }

  }

  submitForm() {

    if (this.name && this.email) {
      this.message = "Form Submitted Successfully!";
      this.messageClass = "success";
    } else {
      this.message = "Please fill all fields!";
      this.messageClass = "error";
    }

  }

}
```

---

# 3️⃣ `app.component.css`

```css
.success {
  color: white;
  background-color: green;
  padding: 10px;
}

.error {
  color: white;
  background-color: red;
  padding: 10px;
}

input {
  padding: 5px;
  margin: 5px;
}
```

---

# 4️⃣ IMPORTANT (Required Step)

Angular forms require **FormsModule**.

Open **`app.config.ts` or app module file** and add FormsModule.

Example if using module:

```typescript
import { FormsModule } from '@angular/forms';
```

and add in imports.

---

# 5️⃣ Run Project

```bash
ng serve
```

Open:

```
http://localhost:4200
```

---

# Output

| Condition     | Result        |
| ------------- | ------------- |
| Name < 3      | Red error     |
| Empty fields  | Red message   |
| Correct input | Green success |

---


