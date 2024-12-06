# 🎨 NG-SCSS-IMPORTS: Modern SCSS in Angular 🚀

Welcome to **NG-SCSS-IMPORTS**, a blazing-fast and modular way to manage SCSS in Angular!  
This project showcases how to leverage SCSS features like `@use` and `@forward` to create reusable, maintainable, and efficient styles. 💅✨

---

## 🌟 Key Concepts: `@use` and `@forward`

### 📜 What are `@use` and `@forward`?

1. **`@use`**:

   - 📂 Loads SCSS files and applies their styles.
   - 🛡️ Adds a **namespace** by default, preventing variable conflicts.
   - 💡 Example:
     ```scss
     @use "variables" as vars;
     body {
       color: vars.$primary-color;
     }
     ```

2. **`@forward`**:
   - 🔄 Re-exports SCSS (e.g., variables, mixins, functions) for global access.
   - 🧩 Simplifies structure by centralizing shared styles.
   - 💡 Example:
     ```scss
     @forward "variables";
     ```

---

### 💪 Benefits Over `@import`

✅ **Namespace Management**: Avoid variable name conflicts.  
✅ **Modularity**: Promotes a clear separation of concerns.  
✅ **Optimized Performance**: Loads files once, reducing redundancy.  
✅ **Tree Shaking**: Only imports the parts you need.  
✅ **Future-Proof**: Fully compatible with modern SCSS standards.

---

## 🏗️ SCSS Setup in Angular

### 📂 File Structure

```
 bls@pc  ~/ng-scss-imports/src > tree
.
├── app
│   ├── app.component.html
│   ├── app.component.scss
│   ├── app.component.spec.ts
│   ├── app.component.ts
│   ├── app.config.ts
│   └── app.routes.ts
├── index.html
├── main.ts
└── styles
    ├── _base.scss
    ├── _functions.scss
    ├── _mixins.scss
    ├── styles.scss
    └── _variables.scss
```

### 🛠️ Why Use Leading Underscores?

Files like `_variables.scss` are **partials**, meaning they are intended to be included in other SCSS files (via `@use` or `@forward`) and won’t generate standalone CSS. This helps keep your build clean and efficient.

---

## ⚙️ Angular Configuration

1. **Add Global SCSS** and **Enable Global Import Paths** in `angular.json`:

```json
{
  "styles": ["src/styles/styles.scss"],
  "stylePreprocessorOptions": {
    "includePaths": ["src/styles"]
  }
}
```

This allows importing SCSS files without relative paths:
scss

```scss
@use "variables"; // instead of @use '../styles/variables'
```

## 🎨 From Variables to Component Styling

### 1️⃣ Define Variables

In \_variables.scss, declare reusable styles:

```scss
$primary-color: #228dff;
$secondary-color: #6c757d;
$font-size-base: 16px;
$black-font-color: #000;
```

### 2️⃣ Forward Variables

Centralize access in styles.scss:

```scss
@forward "variables";
```

### 3️⃣ Use in Components

Import and apply styles in component.scss:

```scss
@use "variables" as *;

:host {
  .main-container {
    &__title {
      color: $black-font-color;
      font-family: "Coda", system-ui;
    }
  }
}
```

## 🌟 Why This Approach Rocks!

✨ Scalability: Perfect for large-scale projects.

✨ Reusability: Centralized styles for easy management.

✨ Consistency: Uniform and predictable styling.

## 🛠️ Getting Started

1. **Clone the Repository**:

   ```bash
   git clone
   ```

2. **Install Dependencies**:

   ```bash
   npm install
   ```

3. **Start the Development Server**:

   ```bash
    ng serve
   ```

4. **Open Your Browser**:

   Your app will be available at `http://localhost:4200`.

---

## 🖌️ Example Output

🌈 Your app will render styles defined globally and in components, like this:

HTML Structure + SCSS Variables = 💖 Magic Styling!

## 🤝 Contributing

Got ideas to improve this example? Feel free to open issues or submit pull requests! 🙌

## 📄 License

This project is licensed under the MIT License.

---

✨ Happy Styling! ✨
