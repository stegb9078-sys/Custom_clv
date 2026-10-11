# 𝗕 Bold Keyboard — Android

Кастомная клавиатура для Android, которая автоматически делает **всё что ты печатаешь жирным** прямо в Telegram, WhatsApp, Discord, ВКонтакте и любом другом приложении.

---

## Как это работает

Ты печатаешь обычный текст → клавиатура автоматически конвертирует его в жирный формат до отправки.

**Два режима (выбираются в `BoldIMEService.java`):**

| Режим | Как работает | Где работает |
|---|---|---|
| `UNICODE_MODE = true` | Вставляет 𝗷𝗶𝗿𝗻𝘆𝗲 Unicode-символы | Везде (любой мессенджер, соцсеть) |
| `UNICODE_MODE = false` | Оборачивает слова в `**жирный**` | Telegram, Discord, WhatsApp |

---

## Установка

### Что нужно
- [Android Studio](https://developer.android.com/studio) (бесплатно)
- Android-телефон или эмулятор

### Шаги

1. **Клонируй репозиторий**
   ```bash
   git clone https://github.com/ТВОЙusername/BoldKeyboard.git
   ```

2. **Открой в Android Studio**
   - File → Open → выбери папку `BoldKeyboard`

3. **Выбери режим** (по желанию)
   - Открой `app/src/main/java/com/boldkeyboard/BoldIMEService.java`
   - Измени строку:
     ```java
     private static final boolean UNICODE_MODE = false; // или true
     ```

4. **Собери APK**
   - Build → Build Bundle(s) / APK(s) → Build APK(s)
   - APK появится в `app/build/outputs/apk/debug/`

5. **Установи на телефон**
   - Перенеси APK на телефон и установи
   - Или подключи телефон по USB и нажми Run ▶ в Android Studio

6. **Включи клавиатуру**
   - Открой приложение Bold Keyboard
   - Нажми **"Открыть настройки клавиатур"**
   - Найди **Bold Keyboard** и включи переключатель
   - Нажми **"Переключить клавиатуру"** и выбери Bold Keyboard

7. **Готово!** Открой Telegram или WhatsApp и начни печатать 🎉

---

## Структура проекта

```
app/src/main/
├── java/com/boldkeyboard/
│   ├── BoldIMEService.java   ← Вся логика клавиатуры
│   └── MainActivity.java     ← Экран-инструкция
├── res/
│   ├── xml/
│   │   ├── method.xml        ← Объявление метода ввода
│   │   ├── qwerty_en.xml     ← Английская раскладка
│   │   └── qwerty_ru.xml     ← Русская раскладка
│   └── layout/
│       ├── keyboard_view.xml ← Внешний вид клавиатуры
│       └── activity_main.xml ← Экран настройки
└── AndroidManifest.xml
```

---

## Настройка внешнего вида

В `res/layout/keyboard_view.xml` можно поменять:
- `android:background` — цвет фона клавиатуры
- `android:keyTextColor` — цвет букв на клавишах
- `android:keyTextSize` — размер букв

---

## Требования

- Android 5.0 (API 21) и выше
- Никаких специальных разрешений не требуется

---

## Лицензия

MIT — делай что хочешь.
