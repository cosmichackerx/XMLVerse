# XMLVerse

---

## 🧩 XML — Android’s Design Language 

---

## 🔤 Definitions (XML)

### 1. What is XML?

**XML (Extensible Markup Language)** is a text-based format defined by the **W3C** and standardized by **ISO/IEC**. It represents structured information in a way that is both **human-readable** and **machine-processable**.

It works by using **tags** to define data — much like a **tree 🌳** with labeled branches and leaves.

In Android, XML is used to define:
- UI layouts
- Resources (strings, colors, dimensions)
- App structure (Manifest, navigation, animations)

Its key role is to separate the app’s:
- 🎨 **Design (XML)** from  
- 🧠 **Logic (Kotlin/Java)**

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of XML as a **"Recipe Card"** or **"Blueprint"**:
- Ingredients = attributes
- Steps = tags
- Android system = chef that cooks your UI

### 🔹 Urdu Analogy
**XML ek naqsha hai 🗺️ — jisme har cheez ka pata hota hai, lekin tasveer nahi hoti.**  
Jaise ek daftar ka file system — har file ka naam aur jagah maloom hoti hai, lekin andar ka content alag hota hai.

### 🧠 Mnemonic: X·M·L → "eXpress, Model, Link"
- **X – eXpress**: Structure your data clearly  
- **M – Model**: Represent real-world entities  
- **L – Link**: Connect systems and components

---

## 💻 Code Examples

### 5. Code Example: Layout & Kotlin Integration

**`res/layout/activity_main.xml` (The Layout)**

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/welcomeText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome, Arslan!"
        android:textSize="20sp" />

    <Button
        android:id="@+id/startButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Start" />

</LinearLayout>
```

**`MainActivity.kt` (The Logic)**

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button = findViewById<Button>(R.id.startButton)
        button.setOnClickListener {
            Toast.makeText(this, "App Started!", Toast.LENGTH_SHORT).show()
        }
    }
}
```

---

## 📚 Core Concepts & Syntax

- **Tag-based Hierarchy**: UI elements are nested like a tree
- **Attributes**: Define properties like size, color, text
- **Strict Format**: Must be well-formed (closed, nested tags)
- **Resource Linking**: Use `@string`, `@color`, `@drawable` for reuse

---

## 🔁 XML vs. HTML

| Concept       | XML                          | HTML                          |
|---------------|-------------------------------|-------------------------------|
| **Purpose**   | Data storage & transport      | Data display                  |
| **Tags**      | User-defined (customizable)   | Predefined (`<p>`, `<div>`)   |
| **Strictness**| Very strict; well-formed      | More lenient                  |

---

## 📂 Core XML File Types in Android

| Location              | Purpose / Usage |
|-----------------------|-----------------|
| `AndroidManifest.xml` | App structure, components, permissions |
| `res/layout/`         | UI screens: `LinearLayout`, `TextView`, `Button` |
| `res/values/`         | Reusable constants:  
• `strings.xml` – Text  
• `colors.xml` – Colors  
• `dimens.xml` – Spacing  
• `styles.xml` / `themes.xml` – Styles & themes  
• `attrs.xml` – Custom view attributes |
| `res/drawable/`       | Graphics:  
• `shape.xml` – Shapes  
• `selector.xml` – State-based drawables  
• `vector.xml` – SVGs  
• `ripple.xml` – Touch feedback |
| `res/menu/`           | Menus, toolbars, options |
| `res/anim/` & `res/animator/` | Animations: fade, rotate, scale |
| `res/navigation/`     | Navigation graphs |
| `res/xml/`            | Configs:  
• `preferences.xml` – Settings  
• `network_security_config.xml` – Security  
• `provider_paths.xml` – File access |

---

## 🧭 Learning Pathway

| Stage       | Focus Area         | Outcome                                      |
|-------------|--------------------|----------------------------------------------|
| **Stage 1** | Syntax & Structure | Understand tags, nesting, attributes         |
| **Stage 2** | Layouts            | Build screens with `LinearLayout`, `ConstraintLayout` |
| **Stage 3** | Styling            | Use `colors.xml`, `dimens.xml`, `styles.xml` |
| **Stage 4** | Linking            | Connect XML to Kotlin/Java via IDs           |
| **Stage 5** | Reusability        | Use `<include>`, styles, fragments           |
| **Stage 6** | Advanced XML       | Learn DataBinding, ViewBinding, custom views |

---

---
## 🧭 Android Follows ISO/W3C Rules Exactly
> Let’s compare a standard ISO XML to Android XML:

```yml
| ISO/W3C Rule                    | Android Example                          | Description               |
| ------------------------------- | ---------------------------------------- | ------------------------- |
| Must start with XML declaration | `<?xml version="1.0" encoding="utf-8"?>` | ✅ Always present          |
| Single root element             | `<LinearLayout>`                         | ✅ Only one root container |
| Nested elements allowed         | `<TextView>` inside `<LinearLayout>`     | ✅ Hierarchical            |
| Attributes inside tags          | `android:layout_width="match_parent"`    | ✅ Used everywhere         |
| Namespaces allowed              | `xmlns:android="..."`                    | ✅ Defines schema          |
| Comments allowed                | `<!-- Comment -->`                       | ✅ Common practice         |
| UTF-8 encoding                  | `encoding="utf-8"`                       | ✅ Android default         |

```

## 🧩 Typical XML Structure (ISO-based)
> Let’s visualize the complete skeleton 👇
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<!-- ① XML Declaration -->

<!DOCTYPE rootElement SYSTEM "example.dtd">
<!-- ② Document Type Declaration (optional, defines validation rules) -->

<rootElement xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- ③ Root Element (must be only ONE) -->

    <childElement attribute1="value1" attribute2="value2">
        <!-- ④ Child Element -->
        Some text content
    </childElement>

    <emptyElement />
    <!-- ⑤ Empty (self-closing) Element -->

</rootElement>
<!-- ⑥ Closing of Root Element -->
```
---
---

## 🧩 `<LinearLayout>` — Android’s Vertical & Horizontal Container 

---

## 🔤 Definitions (LinearLayout)

### What is `<LinearLayout>`?

`<LinearLayout>` is a **ViewGroup** in Android that arranges its child views **in a single direction** — either **vertically** (top to bottom) or **horizontally** (left to right).

It is one of the most commonly used layout containers in Android XML for stacking UI elements in a clean, linear order.

- 🔹 Belongs to: `android.widget.LinearLayout`
- 🔹 Orientation: `vertical` or `horizontal`
- 🔹 Commonly used for: Forms, menus, stacked buttons, vertical screens

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<LinearLayout>` like a **train 🚆**:
- Each child view is a **compartment**
- The train moves in **one direction** — either forward (vertical) or sideways (horizontal)
- All compartments are **lined up one after another**

### 🔹 Urdu Analogy
**`<LinearLayout>` ek seedhi line mein lagay hue dabbon wali rail gaari ki tarah hai 🚋**  
Har child view ek dabba hai — sab ya to upar se neeche (vertical) ya daayein se baayein (horizontal) line mein lagte hain.

### 🧠 Mnemonic: “Linear = Line”
- **Linear** means **in a line**
- So `<LinearLayout>` = **Layout in a line**

---

## 💻 Code Examples

### 📄 Basic Vertical LinearLayout

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome to LinearLayout!" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click Me" />

</LinearLayout>
```

### 📄 Horizontal LinearLayout Example

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    android:gravity="center"
    android:padding="12dp">

    <ImageView
        android:layout_width="48dp"
        android:layout_height="48dp"
        android:src="@drawable/ic_user" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Username"
        android:layout_marginStart="12dp" />

</LinearLayout>
```

---

---

## 🧩 XML Layout Attributes — Explained Line-by-Line 

---

## 🔤 Definitions (Attributes of root layout tag)

These attributes are part of the **root layout tag** in Android XML — typically used in `LinearLayout`, `ConstraintLayout`, or other ViewGroups. They define the layout’s **size**, **orientation**, **padding**, and **context**.

```xml
xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
android:clipToPadding="false"
android:orientation="vertical"
android:padding="24dp"
tools:context=".MainActivity"
```

### 📘 Attribute Breakdown

| Attribute | Meaning |
|----------|---------|
| `xmlns:android` | Declares the Android XML namespace — required for all Android attributes |
| `xmlns:tools` | Declares the tools namespace — used for design-time attributes in Android Studio |
| `android:layout_width="match_parent"` | Makes the layout stretch to fill the parent’s width |
| `android:layout_height="match_parent"` | Makes the layout stretch to fill the parent’s height |
| `android:clipToPadding="false"` | Allows child views to draw outside the padding area |
| `android:orientation="vertical"` | Stacks child views vertically (top to bottom) |
| `android:padding="24dp"` | Adds 24dp space inside the layout edges |
| `tools:context=".MainActivity"` | Tells Android Studio which Activity this layout belongs to (for preview only) |

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of these attributes like **room setup instructions**:
- `layout_width` and `layout_height` = room size  
- `padding` = wall cushioning  
- `orientation` = furniture alignment (vertical or horizontal)  
- `tools:context` = label on the room door for preview

### 🔹 Urdu Analogy
**Ye attributes ek kamray ke naqshay ki tarah hain 🏠 — jisme likha hota hai ke kamra kitna bara hai, furniture kis tarah lagaya gaya hai, aur andar kitni jagah chhodi gayi hai.**  
Jaise `padding` diwaron se doori hai, aur `orientation` furniture ki line ka rukh.

### 🧠 Mnemonic: “W·H·O·P·C·T”
To remember these layout attributes, use:

- **W – Width** (`layout_width`)  
- **H – Height** (`layout_height`)  
- **O – Orientation** (`vertical` or `horizontal`)  
- **P – Padding** (`padding="24dp"`)  
- **C – ClipToPadding** (`false`)  
- **T – Tools Context** (`tools:context`)

---

## 💻 Code Examples

### 📄 Root Layout with Annotated Attributes

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android" <!-- Required Android namespace -->
    xmlns:tools="http://schemas.android.com/tools" <!-- Design-time tools namespace -->
    android:layout_width="match_parent" <!-- Fill parent width -->
    android:layout_height="match_parent" <!-- Fill parent height -->
    android:clipToPadding="false" <!-- Allow drawing beyond padding -->
    android:orientation="vertical" <!-- Stack children vertically -->
    android:padding="24dp" <!-- Add inner spacing -->
    tools:context=".MainActivity"> <!-- Preview context for Android Studio -->

    <!-- Child views go here -->

</LinearLayout>
```

---

---

## 🧩 `<TextView>` — Displaying Text in Android UI 

---

## 🔤 Definitions (TextView)

### What is `<TextView>`?

`<TextView>` is a **widget** in Android used to display **static text** on the screen. It’s one of the most commonly used UI elements for headings, labels, instructions, and messages.

This example shows a styled `TextView` using:

- A predefined **Material style** (`Headline5`)
- Custom **text content**: `"Muhammad Arslan"`
- Custom **text color** from resources: `@color/green_500`
- Layout dimensions: `wrap_content` for both width and height

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<TextView>` like a **label on a jar 🏷️**:
- It doesn’t change
- It tells you what’s inside
- It’s styled to be readable and clear

### 🔹 Urdu Analogy
**`<TextView>` ek daftar ke board par likha hua naam hai 🪧 — jo sirf dikhata hai, lekin badalta nahi.**  
Jaise kisi darwazay par likha ho: “Manager Room” — sirf display hota hai, koi action nahi leta.

### 🧠 Mnemonic: “TextView = View Text Only”
- **TextView** = View-only text  
- No input, no interaction — just display

---

## 💻 Code Examples

### 📄 Styled TextView Example

```xml
<TextView
    style="@style/TextAppearance.MaterialComponents.Headline5"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Muhammad Arslan"
    android:textColor="@color/green_500" />
```

### 📄 Minimal TextView Example

```xml
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello World!" />
```

### 📄 TextView with Padding and Gravity

```xml
<TextView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Centered Text"
    android:gravity="center"
    android:padding="12dp"
    android:textSize="18sp"
    android:textColor="@android:color/holo_blue_dark" />
```

---

---

## 🧩 RelativeLayout — Position-Based UI Design 

---

## 🔤 Definitions (RelativeLayout)

### What is `<RelativeLayout>`?

`<RelativeLayout>` is a **ViewGroup** in Android that allows child views to be **positioned relative to each other** or to the parent container.

Unlike `LinearLayout`, which stacks views in a fixed direction, `RelativeLayout` gives you **flexibility** to place elements:
- Below or beside other views
- Centered horizontally or vertically
- Aligned to parent edges

This layout is ideal for **form designs**, **login screens**, and **custom UI arrangements**.

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<RelativeLayout>` like a **whiteboard 🧭**:
- You can place sticky notes anywhere
- Some notes are placed below others
- Some are aligned to the right or centered

It’s a **freeform canvas** with rules.

### 🔹 Urdu Analogy
**`<RelativeLayout>` ek khaali board ki tarah hai jahan aap har cheez ko doosri cheez ke hawalay se lagate hain 🧾**  
Jaise “ye text title ke neeche ho,” “ye button right corner mein ho” — sab kuch relative positioning se hota hai.

### 🧠 Mnemonic: “Relative = Referenced”
- Views are **positioned by referencing other views**
- Use `layout_below`, `layout_alignParentEnd`, `layout_centerHorizontal`, etc.

---

## 💻 Code Examples

### 📄 Full RelativeLayout Form Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="24dp"
    android:clipToPadding="false"
    tools:context=".MainActivity">

    <!-- Title TextView -->
    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="User Information Form"
        android:textSize="22sp"
        android:textStyle="bold"
        android:textColor="@android:color/holo_green_dark"
        android:layout_centerHorizontal="true" />

    <!-- First Name EditText -->
    <EditText
        android:id="@+id/firstName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter first name"
        android:layout_below="@id/titleText"
        android:layout_marginTop="20dp"
        android:inputType="textPersonName" />

    <!-- Last Name EditText -->
    <EditText
        android:id="@+id/lastName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter last name"
        android:layout_below="@id/firstName"
        android:layout_marginTop="10dp"
        android:inputType="textPersonName" />

    <!-- Email EditText -->
    <EditText
        android:id="@+id/email"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter email address"
        android:layout_below="@id/lastName"
        android:layout_marginTop="10dp"
        android:inputType="textEmailAddress" />

    <!-- Submit Button -->
    <Button
        android:id="@+id/btnSubmit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Submit"
        android:textAllCaps="false"
        android:layout_below="@id/email"
        android:layout_marginTop="16dp"
        android:layout_alignParentEnd="true" />

</RelativeLayout>
```

---

---

## 🧩 `<EditText>` — User Input Field in Android 
---

## 🔤 Definitions (EditText)

### What is `<EditText>`?

`<EditText>` is an Android **input widget** that allows users to **enter and edit text**. It’s commonly used in forms, login screens, and search bars.

In this example:

```xml
<EditText
    android:id="@+id/editText1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:hint="Enter first name" />
```

- `android:id` assigns a unique identifier to reference this field in Kotlin/Java.
- `layout_width` and `layout_height` define the size of the input box.
- `hint` displays placeholder text when the field is empty.

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<EditText>` like a **blank form field 📝**:
- It’s where the user types their response.
- The `hint` is like a **label inside the box** that disappears when typing starts.

### 🔹 Urdu Analogy
**`<EditText>` ek khaali line hai jahan user apna jawab likhta hai ✍️**  
Jaise kisi form mein “Naam likhein” likha hota hai — woh `hint` hota hai. Jab user likhna shuru karta hai, woh likha hua ghaib ho jata hai.

### 🧠 Mnemonic: “Edit + Text = Editable Text”
- **Edit** = User can type or change
- **Text** = The content being entered

---

## 💻 Code Examples

### 📄 Basic EditText with Hint

```xml
<EditText
    android:id="@+id/editText1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:hint="Enter first name" />
```

### 📄 Full-Width EditText with Input Type

```xml
<EditText
    android:id="@+id/inputEmail"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Enter your email"
    android:inputType="textEmailAddress"
    android:padding="12dp" />
```

### 📄 Password Field Example

```xml
<EditText
    android:id="@+id/inputPassword"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Enter password"
    android:inputType="textPassword"
    android:padding="12dp" />
```

---

---

## 🧩 `<Button>` — Triggering Actions in Android UI 

---

## 🔤 Definitions (Button)

### What is `<Button>`?

`<Button>` is an Android **interactive widget** that performs an **action when clicked**. It’s used for submitting forms, navigating screens, triggering events, and more.

In this example:

```xml
<Button
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_below="@id/editText2"
    android:layout_alignParentEnd="true"
    android:text="Submit" />
```

- `layout_below` positions the button below another view (`editText2`)
- `layout_alignParentEnd` aligns it to the right edge of the parent
- `text` sets the label shown on the button

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<Button>` like a **doorbell 🔔**:
- You press it → something happens
- The label tells you what it does (e.g., “Submit”, “Next”, “Login”)

### 🔹 Urdu Analogy
**`<Button>` ek dabane wali switch hai 🖲️ — jise dabane par koi kaam hota hai.**  
Jaise “Submit” button form bhejta hai, “Login” button agla screen kholta hai.

### 🧠 Mnemonic: “Button = Action Trigger”
- **Button** = Triggers logic in Kotlin/Java
- Often paired with `setOnClickListener` in code

---

## 💻 Code Examples

### 📄 Basic Submit Button

```xml
<Button
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Submit" />
```

### 📄 Positioned Button in RelativeLayout

```xml
<Button
    android:id="@+id/btnSubmit"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_below="@id/editText2"
    android:layout_alignParentEnd="true"
    android:text="Submit"
    android:textAllCaps="false"
    android:layout_marginTop="16dp" />
```

### 📄 Kotlin Logic to Handle Button Click

```kotlin
val submitButton = findViewById<Button>(R.id.btnSubmit)
submitButton.setOnClickListener {
    Toast.makeText(this, "Form Submitted!", Toast.LENGTH_SHORT).show()
}
```

---

---

## 🧩 `<ImageView>` — Displaying Images in Android UI 
---

## 🔤 Definitions (ImageView)

### What is `<ImageView>`?

`<ImageView>` is an Android **widget** used to display images such as icons, logos, illustrations, or photos. It supports various image formats and can load resources from the `drawable` folder or external sources.

In this example:

```xml
<ImageView
    android:layout_width="298dp"
    android:layout_height="89dp"
    android:src="@drawable/ic_launcher_foreground" />
```

- `layout_width` and `layout_height` define the image size in density-independent pixels (dp)
- `src` points to the image resource located in `res/drawable/`

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<ImageView>` like a **picture frame 🖼️**:
- You choose what image to show (`src`)
- You decide how big the frame should be (`width`, `height`)
- It’s purely visual — no interaction unless paired with logic

### 🔹 Urdu Analogy
**`<ImageView>` ek tasveer ka frame hai 📸 — jisme aap koi bhi image lagate hain, lekin woh sirf dikhayi jaati hai, dabayi nahi jaati.**  
Jaise app ka logo ya kisi button ke upar icon.

### 🧠 Mnemonic: “ImageView = View Image Only”
- **ImageView** = View-only image  
- Use `src` to load image  
- Use `layout_width` and `layout_height` to size it

---

## 💻 Code Examples

### 📄 Basic ImageView with Drawable Resource

```xml
<ImageView
    android:layout_width="298dp"
    android:layout_height="89dp"
    android:src="@drawable/ic_launcher_foreground" />
```

### 📄 ImageView with Centering and Padding

```xml
<ImageView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:src="@drawable/logo"
    android:layout_gravity="center"
    android:padding="12dp" />
```

### 📄 ImageView with Rounded Corners (via XML shape)

```xml
<ImageView
    android:layout_width="120dp"
    android:layout_height="120dp"
    android:src="@drawable/profile_pic"
    android:background="@drawable/rounded_border"
    android:scaleType="centerCrop" />
```

---

---

## 🧩 `<ConstraintLayout>` — Flexible UI Positioning 
---

## 🔤 Definitions (ConstraintLayout)

### What is `<ConstraintLayout>`?

`<ConstraintLayout>` is a powerful and flexible **ViewGroup** in Android that allows you to **position and size UI elements** relative to each other and to the parent layout using **constraints**.

It replaces older layouts like `RelativeLayout` and `LinearLayout` by offering:
- Flat hierarchy (no nesting needed)
- Precise control over alignment, spacing, and responsiveness
- Better performance for complex UIs

In this example:
- `TextView` is centered horizontally and placed at the top
- `Button` is placed below the `TextView` and also centered

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<ConstraintLayout>` like a **pinboard with strings 🧵**:
- You pin each view to a position using constraints
- You can stretch, align, or anchor views to each other or the board
- It’s like designing with invisible ropes

### 🔹 Urdu Analogy
**`<ConstraintLayout>` ek naqsha hai jisme har cheez ko taaron se baandh kar sahi jagah rakha jata hai 📍**  
Jaise “ye button title ke neeche ho,” “ye text center mein ho” — sab kuch constraints se control hota hai.

### 🧠 Mnemonic: “Constraint = Controlled Placement”
- Use `app:layout_constraintX_toYOf="..."` to define relationships
- Think of each constraint as a **rule** for positioning

---

## 💻 Code Examples

### 📄 Full ConstraintLayout Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome Arslan 👑"
        android:textSize="22sp"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="50dp"/>

    <Button
        android:id="@+id/nextBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Continue 🚀"
        app:layout_constraintTop_toBottomOf="@id/titleText"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:layout_marginTop="24dp"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```

---

---

## 🧩 `<FrameLayout>` — Layered UI Container 
---

## 🔤 Definitions (FrameLayout)

### What is `<FrameLayout>`?

`<FrameLayout>` is a **ViewGroup** in Android that stacks its child views **on top of each other**, like layers. It’s ideal for simple overlays, backgrounds, and single-view screens.

- First child = bottom layer  
- Last child = top layer  
- Use `layout_gravity` to position views inside the frame

It’s commonly used for:
- Splash screens
- Background overlays
- Floating buttons or centered messages

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<FrameLayout>` like a **stack of transparent sheets 📄**:
- You place an image on the bottom
- Then add text or buttons on top
- Each layer is visible depending on its position

### 🔹 Urdu Analogy
**`<FrameLayout>` ek tasveer ke upar chipka hua sticker hai 🖼️ — pehle background lagta hai, phir upar likha hota hai ya button hota hai.**  
Jaise greeting card mein pehle tasveer hoti hai, phir “Welcome” likha hota hai.

### 🧠 Mnemonic: “Frame = Layered Views”
- FrameLayout = Layered layout  
- First added = bottom  
- Last added = top

---

## 💻 Code Examples

### 📄 Example 1: Background Image + Centered Text

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- Child 1 (Bottom Layer) -->
    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:src="@drawable/background_image"
        android:scaleType="centerCrop" />

    <!-- Child 2 (Top Layer) -->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Welcome Arslan 👑"
        android:textColor="@android:color/white"
        android:textSize="24sp"
        android:layout_gravity="center" />

</FrameLayout>
```

---

### 📄 Example 2: Space Theme with Button Overlay

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:src="@drawable/stars"
        android:scaleType="centerCrop" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="✨ Welcome to Space, Arslan 👨‍🚀"
        android:textColor="@android:color/white"
        android:textSize="20sp"
        android:layout_gravity="center" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Launch 🚀"
        android:layout_gravity="bottom|center_horizontal"
        android:layout_marginBottom="32dp" />

</FrameLayout>
```

---

---

## 🧩 `<ScrollView>` — Making Content Scrollable 
---

## 🔤 Definitions (ScrollView)

### What is `<ScrollView>`?

`<ScrollView>` is a **ViewGroup** in Android that enables **vertical scrolling** of its child content when the content height exceeds the screen height.

It wraps a single child layout (usually a `LinearLayout`) and allows all nested views to be scrollable.

Key rules:
- Only **one direct child** allowed (usually a layout like `LinearLayout`)
- Ideal for forms, long articles, or stacked content

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<ScrollView>` like a **scrollable paper roll 📜**:
- You can keep adding content vertically
- The user scrolls to reveal hidden parts
- It’s like a long receipt or a news feed

### 🔹 Urdu Analogy
**`<ScrollView>` ek lambi daftar ki file hai 📄 — jisme neeche neeche aur content hota hai, aur user scroll karke dekh sakta hai.**  
Jaise ek form ya article jo screen se lamba ho.

### 🧠 Mnemonic: “ScrollView = Scrollable View”
- Wrap your layout inside it  
- Enables vertical scrolling  
- Use `LinearLayout` with `wrap_content` height inside

---

## 💻 Code Examples

### 📄 ScrollView with LinearLayout and Multiple Views

```xml
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <!-- Child Views (will scroll) -->
        <TextView
            android:text="Welcome Arslan 👑"
            android:textSize="22sp"
            android:layout_marginBottom="16dp" />

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:src="@drawable/stars"
            android:scaleType="centerCrop" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Continue 🚀" />

        <!-- Repeat more views to see scroll effect -->
        <TextView
            android:text="Lorem ipsum dolor sit amet..."
            android:layout_marginTop="16dp" />

    </LinearLayout>
</ScrollView>
```

## 🌠 Advanced ScrollView Example
> A “Profile & Settings”–style layout with smooth scroll + nested sections.
```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fillViewport="true"
    android:background="#101820"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="24dp"
        android:gravity="center_horizontal">

        <!-- 🔹 Header Image -->
        <ImageView
            android:id="@+id/profileBanner"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:src="@drawable/header_image"
            android:scaleType="centerCrop"
            android:contentDescription="@string/app_name"
            android:background="@drawable/gradient_background"
            android:layout_marginBottom="16dp" />

        <!-- 🔹 Title -->
        <TextView
            android:id="@+id/titleText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Welcome, Arslan 👑"
            android:textColor="#FFFFFF"
            android:textSize="24sp"
            android:textStyle="bold"
            android:layout_marginBottom="12dp" />

        <!-- 🔹 Description -->
        <TextView
            android:id="@+id/subtitleText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Scroll down to explore your dashboard ✨"
            android:textColor="#BBBBBB"
            android:textSize="16sp"
            android:layout_marginBottom="24dp" />

        <!-- 🔹 Checkbox Section -->
        <CheckBox
            android:id="@+id/checkBox"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="I agree to continue 🚀"
            android:textColor="#FFFFFF"
            android:layout_marginBottom="16dp" />

        <!-- 🔹 DatePicker Section -->
        <TextView
            android:text="Select your date of birth:"
            android:textColor="#FFFFFF"
            android:textSize="16sp"
            android:layout_marginBottom="8dp" />

        <DatePicker
            android:id="@+id/datePicker"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginBottom="24dp" />

        <!-- 🔹 NumberPicker Section -->
        <TextView
            android:text="Choose your lucky number:"
            android:textColor="#FFFFFF"
            android:textSize="16sp"
            android:layout_marginBottom="8dp" />

        <NumberPicker
            android:id="@+id/numberPicker"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginBottom="24dp" />

        <!-- 🔹 Action Button -->
        <Button
            android:id="@+id/nextBtn"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Continue 🚀"
            android:backgroundTint="#3F51B5"
            android:textColor="#FFFFFF"
            android:layout_marginBottom="16dp" />

        <!-- 🔹 Footer Image -->
        <ImageView
            android:id="@+id/footerImage"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:src="@drawable/stars"
            android:scaleType="centerCrop"
            android:contentDescription="@string/app_name"
            android:layout_marginTop="16dp"
            android:layout_marginBottom="32dp" />

    </LinearLayout>
</ScrollView>
```

---

---

## 🧩 `<HorizontalScrollView>` — Sideways Scrolling Container (Separated from Previous CardView Concepts)

---

## 🔤 Definitions (HorizontalScrollView)

### What is `<HorizontalScrollView>`?

`<HorizontalScrollView>` is a **ViewGroup** in Android that enables **horizontal scrolling** of its child layout when the content width exceeds the screen width.

It works similarly to `<ScrollView>`, but scrolls **left to right** instead of top to bottom.

Key rules:
- Only **one direct child** allowed (usually a `LinearLayout` with `horizontal` orientation)
- Ideal for image carousels, horizontal menus, or card sliders

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<HorizontalScrollView>` like a **film strip 🎞️**:
- You swipe sideways to view each frame
- Content flows left to right
- Perfect for showcasing items in a row

### 🔹 Urdu Analogy
**`<HorizontalScrollView>` ek tasveeron ki line hai 📷 — jise aap daayein-baayein scroll karke dekhte hain.**  
Jaise ek photo gallery ya horizontal menu.

### 🧠 Mnemonic: “Horizontal = Left to Right Scroll”
- Wrap a horizontal `LinearLayout` inside  
- Use for sideways navigation  
- Great for cards, icons, or banners

---

## 💻 Code Examples

### 📄 Basic HorizontalScrollView with Images

```xml
<HorizontalScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="12dp">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <ImageView
            android:layout_width="120dp"
            android:layout_height="120dp"
            android:src="@drawable/image1"
            android:layout_marginEnd="12dp" />

        <ImageView
            android:layout_width="120dp"
            android:layout_height="120dp"
            android:src="@drawable/image2"
            android:layout_marginEnd="12dp" />

        <ImageView
            android:layout_width="120dp"
            android:layout_height="120dp"
            android:src="@drawable/image3"
            android:layout_marginEnd="12dp" />

    </LinearLayout>
</HorizontalScrollView>
```

---

### 📄 HorizontalScrollView with Buttons

```xml
<HorizontalScrollView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="8dp">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Home" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Projects"
            android:layout_marginStart="12dp" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Explore"
            android:layout_marginStart="12dp" />

    </LinearLayout>
</HorizontalScrollView>
```

---
---

## 🧩 `<NestedScrollView>` — Scrollable Container Inside Coordinators (Separated from Previous HorizontalScrollView Concepts)

---

## 🔤 Definitions (NestedScrollView)

### What is `<NestedScrollView>`?

`<NestedScrollView>` is an advanced version of `<ScrollView>` that supports **nested scrolling** — especially useful when placed inside layouts like `CoordinatorLayout`, `AppBarLayout`, or `CollapsingToolbarLayout`.

It allows smooth interaction between multiple scrollable views and is commonly used in **Material Design** apps where toolbars collapse or float based on scroll behavior.

Key features:
- Supports nested scrolling coordination
- Ideal for layouts with collapsing headers or floating buttons
- Requires AndroidX support library

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<NestedScrollView>` like a **scrollable drawer inside a smart cabinet 🗄️**:
- It scrolls like a normal drawer
- But it also **communicates** with the cabinet (toolbar, app bar)
- Perfect for coordinated UI behavior

### 🔹 Urdu Analogy
**`<NestedScrollView>` ek aisi file hai jo sirf khud nahi hilti, balkay upar ke header ko bhi saath le kar hilti hai 📂**  
Jaise ek app mein scroll karne par toolbar chhup jata hai — ye sab nested scrolling se hota hai.

### 🧠 Mnemonic: “Nested = Scroll + Coordinate”
- NestedScrollView = Scrollable + Interacts with parent layout  
- Use when toolbar or header needs to respond to scroll

---

## 💻 Code Examples

### 📄 Basic NestedScrollView with LinearLayout

```xml
<androidx.core.widget.NestedScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fillViewport="true">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <TextView
            android:text="Welcome Arslan 👑"
            android:textSize="22sp"
            android:layout_marginBottom="16dp" />

        <ImageView
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:src="@drawable/stars"
            android:scaleType="centerCrop" />

        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Continue 🚀" />

        <TextView
            android:text="Lorem ipsum dolor sit amet..."
            android:layout_marginTop="16dp" />

    </LinearLayout>
</androidx.core.widget.NestedScrollView>
```

---

### 📄 NestedScrollView Inside CoordinatorLayout (Advanced)

```xml
<androidx.coordinatorlayout.widget.CoordinatorLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <com.google.android.material.appbar.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <com.google.android.material.appbar.CollapsingToolbarLayout
            android:layout_width="match_parent"
            android:layout_height="200dp"
            app:layout_scrollFlags="scroll|exitUntilCollapsed">

            <!-- Toolbar and Image here -->

        </com.google.android.material.appbar.CollapsingToolbarLayout>
    </com.google.android.material.appbar.AppBarLayout>

    <androidx.core.widget.NestedScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:layout_behavior="@string/appbar_scrolling_view_behavior">

        <!-- Scrollable content here -->

    </androidx.core.widget.NestedScrollView>
</androidx.coordinatorlayout.widget.CoordinatorLayout>
```

---
---

## 🧩 `<CardView>` — Material Design Container with Elevation 
---

## 🔤 Definitions (CardView)

### What is `<CardView>`?

`<CardView>` is a **UI container** from the AndroidX library that wraps content inside a **rounded rectangle with shadow (elevation)**. It follows **Material Design** principles and is ideal for displaying grouped content like:

- Profile cards
- Dashboards
- Project summaries
- Scrollable lists

Key features:
- `cardCornerRadius`: Rounds the corners
- `cardElevation`: Adds shadow depth
- `cardBackgroundColor`: Sets background color

---

## 🧠 Mnemonics & Analogies (English + Urdu)

### 🔹 English Analogy
Think of `<CardView>` like a **physical card or tile 🧾**:
- It holds grouped content
- It casts a shadow (elevation)
- It’s visually separated from the background

### 🔹 Urdu Analogy
**`<CardView>` ek visiting card ya dashboard tile ki tarah hai 🪪 — jisme ek hi jagah par naam, tasveer, aur button hota hai.**  
Jaise ek profile card ya project summary card.

### 🧠 Mnemonic: “Card = Compact + Elevated”
- **Card** = Compact container  
- **Elevation** = Shadow for depth  
- **Rounded corners** = Modern UI look

---

## 💻 Code Examples

### 📄 Basic CardView with Image, Text, and Button

```xml
<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="12dp"
    app:cardCornerRadius="16dp"
    app:cardElevation="8dp"
    app:cardBackgroundColor="#1E1E2E">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <TextView
            android:id="@+id/cardTitle"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Welcome Arslan 👑"
            android:textSize="20sp"
            android:textStyle="bold"
            android:textColor="#FFFFFF" />

        <TextView
            android:id="@+id/cardDesc"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="You're building something futuristic 💫"
            android:textColor="#BBBBBB"
            android:layout_marginTop="4dp" />

        <ImageView
            android:id="@+id/cardImage"
            android:layout_width="match_parent"
            android:layout_height="180dp"
            android:layout_marginTop="12dp"
            android:src="@drawable/stars"
            android:scaleType="centerCrop" />

        <Button
            android:id="@+id/cardButton"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Explore 🚀"
            android:layout_gravity="center_horizontal"
            android:layout_marginTop="16dp"
            android:backgroundTint="#3F51B5"
            android:textColor="#FFFFFF" />

    </LinearLayout>
</androidx.cardview.widget.CardView>
```

---

### 📄 Enhanced Scrollable Card List

```xml
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="12dp"
    android:background="#101820">

    <LinearLayout
        android:orientation="vertical"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!-- Card 1 -->
        <androidx.cardview.widget.CardView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="16dp"
            app:cardCornerRadius="18dp"
            app:cardElevation="10dp"
            app:cardBackgroundColor="#1E1E2E">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="vertical"
                android:padding="16dp">

                <TextView
                    android:text="🚀 Project: CoroutineVerse"
                    android:textColor="#FFFFFF"
                    android:textSize="20sp"
                    android:textStyle="bold"/>

                <TextView
                    android:text="Your GitHub repo for async greatness ✨"
                    android:textColor="#AAAAAA"
                    android:layout_marginTop="4dp"/>

            </LinearLayout>
        </androidx.cardview.widget.CardView>

        <!-- Card 2 -->
        <androidx.cardview.widget.CardView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="16dp"
            app:cardCornerRadius="18dp"
            app:cardElevation="10dp"
            app:cardBackgroundColor="#292940">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="vertical"
                android:padding="16dp">

                <TextView
                    android:text="🌌 Topic: Polarization"
                    android:textColor="#FFFFFF"
                    android:textSize="20sp"
                    android:textStyle="bold"/>

                <TextView
                    android:text="Electromagnetic beauty through waves 🌊"
                    android:textColor="#AAAAAA"
                    android:layout_marginTop="4dp"/>

            </LinearLayout>
        </androidx.cardview.widget.CardView>

    </LinearLayout>
</ScrollView>
```

---

### 📄 Dashboard-Style Grid of Cards (Advanced)

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#0F172A"
    tools:context=".DashboardActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="16dp">

        <!-- Section Title -->
        <TextView
            android:id="@+id/sectionTitle"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Welcome, Arslan 👑"
            android:textColor="#FFFFFF"
            android:textSize="24sp"
            android:textStyle="bold"
            android:layout_marginBottom="20dp" />

        <!-- Grid of Cards -->
        <GridLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:columnCount="2"
            android:rowCount="3"
            android:orientation="horizontal"
            android:alignmentMode="alignMargins"
            android:rowOrderPreserved="false"
            android:columnOrderPreserved="false">

            <!-- Card 1 -->
            <androidx.cardview.widget.CardView
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_margin="8dp"
                android:layout_columnWeight="1"
                app:cardCornerRadius="20dp"
                app:cardElevation="12dp"
                app:cardBackgroundColor="#1E293B"
                app:cardUseCompatPadding="true"
                android:foreground="?attr/selectableItemBackground">

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical"
                    android:padding="16dp"
                    android:gravity="center">

                    <ImageView
                        android:layout_width="64dp"
                        android:layout_height="64dp"
                        android:src="@drawable/ic_code"
                        android:contentDescription="@string/app_name"
                        android:tint="#60A5FA" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Projects"
                        android:textColor="#FFFFFF"
                        android:textStyle="bold"
                        android:layout_marginTop="12dp" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="View your coding works 💻"
                        android:textColor="#A0A0A0"
                        android:textSize="12sp"
                        android:layout_marginTop="4dp" />

                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <!-- Card 2 -->
            <androidx.cardview.widget.CardView
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_margin="8dp"
                android:layout_columnWeight="1"
                app:cardCornerRadius="20dp"
                app:cardElevation="12dp"
                app:cardBackgroundColor="#1E293B"
                app:cardUseCompatPadding="true">

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical"
                    android:padding="16dp"
                    android:gravity="center">

                    <ImageView
                        android:layout_width="64dp"
                        android:layout_height="64dp"
                        android:src="@drawable/ic_science"
                        android:tint="#38BDF8" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Research"
                        android:textColor="#FFFFFF"
                        android:textStyle="bold"
                        android:layout_marginTop="12dp" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Science & Innovation 🔬"
                        android:textColor="#A0A0A0"
                        android:textSize="12sp"
                        android:layout_marginTop="4dp" />

                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <!-- Card 3 -->
            <androidx.cardview.widget.CardView
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_margin="8dp"
                android:layout_columnWeight="1"
                app:cardCornerRadius="20dp"
                app:cardElevation="12dp"
                app:cardBackgroundColor="#1E293B">

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical"
                    android:padding="16dp"
                    android:gravity="center">

                    <ImageView
                        android:layout_width="64dp"
                        android:layout_height="64dp"
                        android:src="@drawable/ic_earth"
                        android:tint="#34D399" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Explore"
                        android:textColor="#FFFFFF"
                        android:textStyle="bold"
                        android:layout_marginTop="12dp" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="World & Space 🌍"
                        android:textColor="#A0A0A0"
                        android:textSize="12sp"
                        android:layout_marginTop="4dp" />

                </LinearLayout>
            </androidx.cardview.widget.CardView>

            <!-- Card 4 -->
            <androidx.cardview.widget.CardView
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_margin="8dp"
                android:layout_columnWeight="1"
                app:cardCornerRadius="20dp"
                app:cardElevation="12dp"
                app:cardBackgroundColor="#1E293B">

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:orientation="vertical"
                    android:padding="16dp"
                    android:gravity="center">

                    <ImageView
                        android:layout_width="64dp"
                        android:layout_height="64dp"
                        android:src="@drawable/ic_brain"
                        android:tint="#F87171" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Mind Zone"
                        android:textColor="#FFFFFF"
                        android:textStyle="bold"
                        android:layout_marginTop="12dp" />

                    <TextView
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="Dark Psychology 🧠"
                        android:textColor="#A0A0A0"
                        android:textSize="12sp"
                        android:layout_marginTop="4dp" />

                </LinearLayout>
            </androidx.cardview.widget.CardView>

        </GridLayout>
    </LinearLayout>
</ScrollView>
```

---
