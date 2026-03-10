---

# 1️⃣ `app.component.html`

```html
<div class="container">
  <h2>Job Registration Form</h2>

  <form #jobForm="ngForm" (ngSubmit)="submitForm(jobForm)">

    <!-- Full Name -->
    <label>Full Name *</label>
    <input type="text"
           name="fullname"
           [(ngModel)]="user.fullname"
           required
           minlength="3">

    <div class="error" *ngIf="jobForm.submitted && !user.fullname">
      Name is required
    </div>


    <!-- Email -->
    <label>Email *</label>
    <input type="email"
           name="email"
           [(ngModel)]="user.email"
           required>

    <div class="error" *ngIf="jobForm.submitted && !user.email">
      Email is required
    </div>


    <!-- Phone -->
    <label>Phone *</label>
    <input type="text"
           name="phone"
           [(ngModel)]="user.phone"
           required>


    <!-- Qualification -->
    <label>Qualification *</label>
    <select name="qualification"
            [(ngModel)]="user.qualification"
            required>

      <option value="">--Select--</option>
      <option>B.Tech</option>
      <option>M.Tech</option>
      <option>MCA</option>
      <option>B.Sc</option>

    </select>


    <!-- Gender -->
    <label>Gender *</label>

    <label>
      <input type="radio"
             name="gender"
             value="Male"
             [(ngModel)]="user.gender"> Male
    </label>

    <label>
      <input type="radio"
             name="gender"
             value="Female"
             [(ngModel)]="user.gender"> Female
    </label>


    <!-- Experience -->
    <label>Experience *</label>
    <input type="number"
           name="experience"
           [(ngModel)]="user.experience"
           required>


    <!-- Position -->
    <label>Job Position *</label>
    <select name="position"
            [(ngModel)]="user.position"
            required>

      <option value="">--Select--</option>
      <option>Software Developer</option>
      <option>Senior Developer</option>
      <option>Project Manager</option>

    </select>


    <!-- Skills -->
    <label>Skills *</label>

    <label>
      <input type="checkbox" [(ngModel)]="user.skills.javascript" name="javascript"> JavaScript
    </label>

    <label>
      <input type="checkbox" [(ngModel)]="user.skills.python" name="python"> Python
    </label>

    <label>
      <input type="checkbox" [(ngModel)]="user.skills.java" name="java"> Java
    </label>


    <!-- Salary -->
    <label>Expected Salary *</label>
    <input type="number"
           name="salary"
           [(ngModel)]="user.salary"
           required>


    <br><br>

    <button type="submit">
      Register
    </button>

  </form>

  <div class="success" *ngIf="successMessage">
    {{successMessage}}
  </div>

</div>
```

---

# 2️⃣ `app.component.ts`

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

  successMessage = "";

  user: any = {
    skills: {}
  };

  getSkillsSelected() {
    return Object.values(this.user.skills).some(skill => skill === true);
  }

  submitForm(form: any) {

    if (form.valid && this.getSkillsSelected()) {

      const registrationData = {
        ...this.user,
        skills: Object.keys(this.user.skills)
               .filter(skill => this.user.skills[skill])
      };

      console.log("Registration Data:", registrationData);

      this.successMessage =
        "Job Registration Successful! We will contact you soon.";

      setTimeout(() => {
        form.resetForm();
        this.user = { skills: {} };
        this.successMessage = "";
      }, 3000);

    } else {
      alert("Please fill all fields and select at least one skill");
    }

  }

}
```

---

# 3️⃣ `app.component.css`

```css
.container{
 width:600px;
 margin:auto;
 background:white;
 padding:30px;
 border-radius:8px;
 box-shadow:0 4px 20px rgba(0,0,0,0.1);
}

input,select,textarea{
 padding:10px;
 margin:8px 0;
 border:1px solid #ddd;
 border-radius:4px;
 width:100%;
}

button{
 background:#667eea;
 color:white;
 padding:12px;
 border:none;
 border-radius:4px;
 width:100%;
}

.success{
 color:green;
 font-weight:bold;
 margin-top:20px;
}

.error{
 color:red;
 font-size:12px;
}
```

---

# 4️⃣ Run Project

```bash
ng serve
```

Open

```
http://localhost:4200
```

---

# Result

Your **AngularJS Job Registration Form** is now converted into **Angular (Standalone Component)** structure.

---

