# Розробка мобільних застосунків

# Практична робота №1.4 - Робота із кольором та локалізацією в ОС Android.

### Мета
Отримати досвід роботи із використанням значень рядків і кольорів та зміною локалізації у додатку.

### Крок 1: Додавання коду до попереднього проекту.
Крок 1.1: Додаю кольори до файлу ```colors.xml```.
```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#131313</color>
    <color name="white">#FFFFFFFF</color>

    <color name="deep_teal">#217074</color>
    <color name="dark_sea_green">#37745B</color>
    <color name="lauren_green">#8B9D77</color>
    <color name="platinum">#E7EAEF</color>
    <color name="apricot">#EDC5AB</color>
</resources>
```
Крок 1.2: Додаю теми для активностей ```themes.xml```
```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Base.Theme.RMZ3" parent="Theme.Material3.DayNight.NoActionBar">
        <!-- Customize your light theme here. -->
        <item name="android:background">@color/apricot</item>
        <item name="android:textColor">@color/black</item>


    </style>

    <style name="Theme.RMZ3" parent="Base.Theme.RMZ3" />
</resources>

<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Base.Theme.RMZ3" parent="Theme.Material3.DayNight.NoActionBar">
        <!-- Customize your dark theme here. -->
        <item name="android:background">@color/black</item>
        <item name="android:textColor">@color/white</item>

        <item name="android:thumbTint">#FFFFFF</item>
        <item name="android:trackTint">#BDBDBD</item>
    </style>
</resources>
```
Крок 1.3: В методі ```onCreate()``` додаю функціонал перемикання теми.
```java
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        themeSwitch = findViewById(R.id.switch_theme);
        themeSwitch.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
                if(isChecked){
                    getDelegate().setLocalNightMode(AppCompatDelegate.MODE_NIGHT_YES);
                }else{
                    getDelegate().setLocalNightMode(AppCompatDelegate.MODE_NIGHT_NO);
                }
            }
        });
    }
```

### Крок 2: Додавання компонентів в MainActivity
-В файлі \app\src\main\res\layout\activity_main.xml, додаю новый View

![image](https://github.com/SSovyshka/RMZ_3/assets/91850335/dc40f129-4417-4b4e-a216-b5ab329b23d2)

```
    <androidx.appcompat.widget.SwitchCompat
        android:id="@+id/switch_theme"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="20dp"
        android:minWidth="48dp"
        android:minHeight="48dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="80dp"
        android:layout_marginEnd="8dp"
        android:textSize="16sp"
        android:text="@string/lorem_ipsum"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
```


### Крок 3: Робочий додаток
Додаток працює як очікувано, змінюючи тему при перемиканні.



### Висновок
Практична робота демонструє базові кроки взаємодії з кольорами з використанням Android Studio.
