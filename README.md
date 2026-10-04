# KxushOS — StableV1

🌐 **Language / Язык:** [🇷🇺 Русский](#-русский) · [🇬🇧 English](#-english)

> ## ⚠️ This is NOT a Windows build / Это НЕ сборка Windows!
> **RU:** Это **файл ответов** (`autounattend.xml`) для автоматической установки Windows 10/11 с оригинального ISO. Он не содержит файлов Windows, не изменяет образ и не распространяет чужой софт. Задача — удобство, комфорт и повседневное использование системы.
>
> **EN:** This is an **answer file** (`autounattend.xml`) for unattended installation of Windows 10/11 from an **original ISO**. It contains no Windows files, does not modify the image and does not redistribute any third-party software. Its purpose is convenience, comfort and everyday use.

---

# 🇷🇺 Русский

## 📌 Что это

`KxushOS_StableV1.xml` — файл автоматической установки (answer file), созданный на базе [Unattend Generator](https://schneegans.de/windows/unattend-generator/) с дополнительными собственными твиками реестра. Он:

- убирает лишний мусор и рекламу из системы;
- настраивает интерфейс и проводник «под себя»;
- ускоряет отклик системы;
- пропускает назойливые экраны при первой настройке (OOBE).

## 🚀 Как использовать

1. Скачайте **оригинальный ISO** Windows с сайта Microsoft.
2. Переименуйте файл в **`autounattend.xml`**.
3. Запишите ISO на флешку (Rufus, Ventoy и т. д.) и положите `autounattend.xml` **в корень флешки**.
4. Загрузитесь с флешки и установите Windows.

> 💡 Выбор редакции, языка и разметки диска остаётся **интерактивным** — ничего не форматируется автоматически.

## 🛡️ Windows Defender и Microsoft Edge

В этом файле ответов **Windows Defender НЕ отключается, а Microsoft Edge НЕ удаляется**.

Чтобы **отключить Windows Defender** и **удалить Edge**, нужны **дополнительные твики**, которые будут выложены на **Google Drive**:

📎 **Ссылка на Google Drive:** `https://drive.google.com/file/d/1_nfshYgy7PgGXRfYZj11-SbT-gxFU-o0/view?usp=sharing`

Авторы Твиков: Remove Edge - https://github.com/ShadowWhisperer ; Disable Windows Defender - https://github.com/ionuttbara

## 📝 Список изменений

### 🔧 Установка и OOBE
- Обход проверок **TPM, Secure Boot и RAM** (установка на «неподдерживаемое» железо).
- Обход обязательного подключения к сети и Microsoft-аккаунту (**BypassNRO**) — локальная учётная запись.
- Имя компьютера: **KxushOS**.
- Скрыты экраны: EULA, настройка Wi-Fi, онлайн-аккаунты; «экспресс-настройки» отключены.
- Срок действия пароля — **без ограничения**.
- Отключены залипание клавиш (Sticky Keys) и повышенная точность указателя мыши.

### 🗑️ Удалённые приложения (UWP)
3D Viewer, Bing Search, Камера, Clipchamp, Часы/Будильники, Copilot, Cortana, Dev Home, Family, Центр отзывов (Feedback Hub), Game Assist (Edge), Техническая поддержка (Get Help), Советы (Get Started), Почта и Календарь, Карты, Mixed Reality Portal, Новости, Microsoft 365 (Office Hub), OneNote, Outlook (новый), Paint 3D, People, Power Automate, Быстрая помощь (Quick Assist), Skype, Solitaire Collection, Sticky Notes, Teams, To Do, Диктофон, Кошелёк (Wallet), Погода, Связь с телефоном (Phone Link), Кино и ТВ (Zune Video).

### 🗑️ Удалённые компоненты Windows (Capabilities)
Рукописный ввод, Internet Explorer, Панель математического ввода, OneSync, OpenSSH Client, Quick Assist, Распознавание речи и синтез речи (Speech / TTS), Средство записи действий (Steps Recorder), **Windows Hello Face** (распознавание лица).

### 🗑️ Отключённые / удалённые функции (Features)
Медиа-компоненты (MediaPlayback), **PowerShell 2.0**, **Recall**.

### 🗑️ Прочее удалено
- **OneDrive** (установщик и ярлык), а также автозапуск OneDrive для новых пользователей.
- Ярлык **Microsoft Edge** с рабочего стола (сам Edge остаётся).
- Папка **Windows.old** после установки.
- Задачи автоустановки DevHome и Outlook из планировщика обновлений.
- Символические ссылки/junction-точки в системных и пользовательских каталогах.
- Автоматическая установка Teams/Chat.

### 🔒 Приватность и «чистота» системы
- Отключены: реклама в меню «Пуск», рекомендации приложений, **Windows Consumer Features**, Cloud Optimized Content, контент ContentDeliveryManager.
- Отключён **Bing в поиске** и подсказки в поле поиска.
- Отключены **Виджеты** и «Новости и интересы».
- Отключён **Copilot** (политика).
- Отключён **Game DVR / Xbox Game Bar** запись.
- Edge: скрыт первый запуск, отключены Startup Boost и фоновый режим.

### ⚠️ Безопасность и обновления *(важно прочитать)*
- Отключён **SmartScreen** (система, Edge, веб-контент приложений).
- Отключён **Smart App Control (SAC)**.
- **Автоматические обновления Windows отключены** (`NoAutoUpdate`), поиск драйверов через Windows Update отключён. Обновляйтесь вручную!
- Отключено **восстановление системы**.
- Отключено автоматическое **шифрование устройства BitLocker**.
- Включён **Удалённый рабочий стол (RDP)** и разрешено правило брандмауэра для него.
- Усилены права на диск C: (убрана группа «Прошедшие проверку» из корня).
- Разрешено выполнение скриптов PowerShell (**RemoteSigned**).
- Запрещена автоматическая перезагрузка при наличии вошедшего пользователя.

> ℹ️ Всё это — осознанный выбор «для удобства». Если вы не уверены, нужны ли вам эти изменения, **проверьте файл перед использованием** и при необходимости отредактируйте его.

### 🎨 Интерфейс и проводник
- **Тёмная тема** системы и приложений, акцентный цвет `#0078D4`.
- Классическое **контекстное меню** (как в Windows 10).
- Проводник открывается на **«Этот компьютер»**; отображаются **расширения файлов** и скрытые файлы.
- Компактный вид проводника.
- Убраны «Главная» и «Галерея» из панели навигации; отключены «Недавние» и «Часто используемые».
- Из «Этого компьютера» скрыты папки: Видео, Документы, Загрузки, Изображения, Музыка, Рабочий стол, Объёмные объекты.
- В контекстное меню добавлены: **«Стать владельцем»**, **«Копировать в папку»**, **«Переместить в папку»**.
- Убрана надпись « — Ярлык» у новых ярлыков.
- Классическое **«Просмотр фотографий Windows»** (Photo Viewer) возвращено.
- На рабочем столе только **Корзина** и **Этот компьютер**.

### 🧭 Панель задач и «Пуск»
- На панели задач закреплён только **Проводник**.
- Поиск — в виде **иконки**; кнопка «Представление задач» скрыта.
- Включена кнопка **«Завершить задачу»** в контекстном меню панели задач.
- «Пуск»: закреплены только **Проводник** и **Параметры**; рядом с кнопкой питания — Документы, Загрузки, Изображения.
- Отключён акрил (размытие) на экране входа.

### ⚡ Производительность и отзывчивость
- Задержка меню — `0 мс`, быстрые подсказки.
- Быстрый повтор клавиш (минимальная задержка, максимальная скорость).
- Таймаут зависших приложений и служб при выключении — **2 секунды**; автозавершение задач при выключении.
- Отключён сетевой троттлинг мультимедиа, `SystemResponsiveness = 0`.
- Повышенный приоритет для игр (GPU/CPU/диск).
- Оптимизация приоритета процессов переднего плана (`Win32PrioritySeparation`).
- Отключены короткие имена 8.3 и обновление времени последнего доступа к файлам (меньше нагрузка на NTFS).
- Оптимизация полноэкранного режима (меньше input lag в играх).
- Включены **длинные пути** (Long Paths).
- Отключён таймаут выключения экрана на экране блокировки.

## ⚖️ Отказ от ответственности

- Файл предоставляется **«как есть»**, вы используете его **на свой страх и риск**.
- Автор не несёт ответственности за потерю данных, проблемы с безопасностью или нестабильность системы.
- Для установки вам нужна **собственная лицензия Windows**. Ключ в файле — пустой шаблон (`00000-00000-…`).
- Перед установкой **сделайте резервную копию** важных данных.

---

# 🇬🇧 English

## 📌 What is this

`KxushOS_StableV1.xml` is an unattended-installation answer file built with [Unattend Generator](https://schneegans.de/windows/unattend-generator/) plus additional custom registry tweaks. It:

- strips bloatware and ads from the system;
- sets up the UI and File Explorer the way a daily user wants;
- improves system responsiveness;
- skips the annoying first-run (OOBE) screens.

## 🚀 How to use

1. Download an **original Windows ISO** from Microsoft.
2. Rename the file to **`autounattend.xml`**.
3. Write the ISO to a USB drive (Rufus, Ventoy, etc.) and put `autounattend.xml` in the **root of the drive**.
4. Boot from the drive and install Windows.

> 💡 Edition, language and disk partitioning remain **interactive** — nothing is formatted automatically.

## 🛡️ Windows Defender & Microsoft Edge

In this answer file **Windows Defender is NOT disabled and Microsoft Edge is NOT removed**.

To **disable Windows Defender** and **remove Edge**, you need **additional tweaks**, which will be uploaded to **Google Drive**:

📎 **Google Drive link:** `https://drive.google.com/file/d/1_nfshYgy7PgGXRfYZj11-SbT-gxFU-o0/view?usp=drive_link`

Tweaks Dev: Remove Edge - https://github.com/ShadowWhisperer ; Disable Windows Defender - https://github.com/ionuttbara

## 📝 Changelog

### 🔧 Setup & OOBE
- Bypass for **TPM, Secure Boot and RAM** requirement checks (install on "unsupported" hardware).
- Bypass of the mandatory network / Microsoft account step (**BypassNRO**) — local account.
- Computer name: **KxushOS**.
- Hidden screens: EULA, Wi-Fi setup, online accounts; express settings disabled.
- Password expiration set to **unlimited**.
- Sticky Keys and enhanced pointer precision disabled.

### 🗑️ Removed apps (UWP)
3D Viewer, Bing Search, Camera, Clipchamp, Clock/Alarms, Copilot, Cortana, Dev Home, Family, Feedback Hub, Game Assist (Edge), Get Help, Get Started (Tips), Mail & Calendar, Maps, Mixed Reality Portal, News, Microsoft 365 (Office Hub), OneNote, Outlook (new), Paint 3D, People, Power Automate, Quick Assist, Skype, Solitaire Collection, Sticky Notes, Teams, To Do, Voice Recorder, Wallet, Weather, Phone Link, Movies & TV (Zune Video).

### 🗑️ Removed Windows capabilities
Handwriting, Internet Explorer, Math Input Panel, OneSync, OpenSSH Client, Quick Assist, Speech recognition & Text-to-speech, Steps Recorder, **Windows Hello Face**.

### 🗑️ Disabled / removed Windows features
Media features (MediaPlayback), **PowerShell 2.0**, **Recall**.

### 🗑️ Other removals
- **OneDrive** (installer and shortcut) and its autorun for new users.
- **Microsoft Edge** desktop shortcut (Edge itself stays installed).
- **Windows.old** folder after installation.
- DevHome and Outlook auto-install tasks from the update orchestrator.
- Junction / reparse points in system and user directories.
- Automatic Teams/Chat installation.

### 🔒 Privacy & cleanliness
- Disabled: Start menu ads, app suggestions, **Windows Consumer Features**, Cloud Optimized Content, ContentDeliveryManager content.
- **Bing in search** and search box suggestions disabled.
- **Widgets** and "News and Interests" disabled.
- **Copilot** disabled (policy).
- **Game DVR / Game Bar** capture disabled.
- Edge: first-run experience hidden, Startup Boost and background mode disabled.

### ⚠️ Security & updates *(please read)*
- **SmartScreen** disabled (system, Edge, app web content evaluation).
- **Smart App Control (SAC)** disabled.
- **Automatic Windows Updates are disabled** (`NoAutoUpdate`), driver search via Windows Update disabled. Update manually!
- **System Restore** disabled.
- Automatic **BitLocker device encryption** prevented.
- **Remote Desktop (RDP)** enabled, with the matching firewall rule group.
- Hardened ACL on the system drive (Authenticated Users removed from the C:\ root).
- PowerShell script execution allowed (**RemoteSigned**).
- Automatic restart disabled while a user is logged on.

> ℹ️ These are deliberate "convenience" choices. If you are unsure whether you want them, **review the file before use** and edit it as needed.

### 🎨 UI & Explorer
- System-wide **dark theme** (system + apps), accent color `#0078D4`.
- Classic **context menu** (Windows 10 style).
- Explorer opens on **This PC**; **file extensions** and hidden files are shown.
- Compact view in Explorer.
- "Home" and "Gallery" removed from the navigation pane; "Recent" and "Frequent" disabled.
- Hidden from This PC: Videos, Documents, Downloads, Pictures, Music, Desktop, 3D Objects.
- Context menu additions: **Take Ownership**, **Copy to folder**, **Move to folder**.
- "– Shortcut" suffix removed from new shortcuts.
- Classic **Windows Photo Viewer** restored.
- Desktop shows only **Recycle Bin** and **This PC**.

### 🧭 Taskbar & Start
- Only **File Explorer** is pinned to the taskbar.
- Search shown as an **icon**; Task View button hidden.
- **End Task** enabled in the taskbar context menu.
- Start: only **File Explorer** and **Settings** pinned; Documents, Downloads, Pictures next to the power button.
- Acrylic blur on the sign-in screen disabled.

### ⚡ Performance & responsiveness
- Menu show delay `0 ms`, faster tooltips.
- Fast keyboard repeat (minimum delay, maximum rate).
- Hung app / service shutdown timeout set to **2 seconds**; auto-end tasks on shutdown.
- Multimedia network throttling disabled, `SystemResponsiveness = 0`.
- Higher priority for games (GPU/CPU/disk I/O).
- Foreground process priority tuned (`Win32PrioritySeparation`).
- 8.3 short names and last-access timestamp updates disabled (lower NTFS overhead).
- Fullscreen behavior tweaks (lower input lag in games).
- **Long paths** enabled.
- Console lock screen display timeout disabled.

## ⚖️ Disclaimer

- Provided **"as is"**, use it **at your own risk**.
- The author is not responsible for data loss, security issues or system instability.
- You need your **own Windows license**. The key in the file is an empty placeholder (`00000-00000-…`).
- **Back up** your important data before installing.
