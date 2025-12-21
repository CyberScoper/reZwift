# reZwift - Руководство для пользователей

<img width="128" height="128" alt="telegram-cloud-document-2-5226687535207451926" src="https://github.com/user-attachments/assets/e168bed5-820b-4c36-b19d-3c10f24855c5" />

**reZwift** - это альтернативный способ использования Zwift, который даёт вам максимальную свободу в виртуальных тренировках. Работает без подписки Zwift, позволяет выбирать любые карты и маршруты в любое время, поддерживает загрузку тренировок в Garmin Connect и Strava без VPN.

## 🚀 Быстрый старт

### Что вам понадобится
- ✅ **Официальный клиент Zwift** (скачать с [zwift.com](https://www.zwift.com) или из [Google Drive](https://drive.google.com/drive/folders/1KCwydAtaasiZHThbshZxzUvMoGEoQg1v))
- ✅ **Операционная система**: Windows 10/11, macOS, Android
- ❌ **Подписка Zwift НЕ требуется**

### Подключение за 5 минут

1. **Скачайте скрипт настройки**: [configure_client.bat](https://drive.google.com/drive/folders/1KCwydAtaasiZHThbshZxzUvMoGEoQg1v)
2. **Запустите от имени администратора**: ПКМ → "Запуск от имени администратора"
   <img width="779" height="553" alt="telegram-cloud-document-2-5226687535207451889" src="https://github.com/user-attachments/assets/d42a935c-4e79-4412-9615-a38c86e5c636" />
4. **Установите Zwift** в папку `C:\Program Files (x86)\Zwift\`
5. **Запустите Zwift** - откроется веб-лаунчер reZwift
6. **Создайте аккаунт**: любой email и пароль (работает только на reZwift)

**Готово!** 🚴‍♂️

## 📋 Подробная настройка клиента

#### Windows
1. **Запустите `configure_client.bat` от имени администратора**
2. Скрипт автоматически:
   - Добавит серверы reZwift в `hosts`
   - Импортирует SSL-сертификат
   - Модифицирует `cacert.pem` в папке Zwift
<img width="594" height="301" alt="telegram-cloud-document-2-5226687535207451896" src="https://github.com/user-attachments/assets/30e2380b-0919-4c27-ab0b-448aab2303a1" />

#### macOS
1. **Импортируйте сертификат**:
   ```bash
   # В Keychain Access импортируйте cert-zwift-com.pem
<img width="1450" height="286" alt="image" src="https://github.com/user-attachments/assets/33d2b8f2-1533-4415-bb76-e2fc6f44d2c2" />


   # Установите доверие: "Always Trust"
<img width="1756" height="860" alt="image" src="https://github.com/user-attachments/assets/e27aa7c3-3923-4c4d-b933-3176e4bacf51" />


  
2. **Добавьте в hosts**:
<img width="913" height="483" alt="Снимок экрана 2025-11-12 в 02 32 50" src="https://github.com/user-attachments/assets/7064a888-070f-49c4-83f2-a66aa6ef00d2" />



   ```
   185.217.199.111 us-or-rly101.zwift.com secure.zwift.com cdn.zwift.com launcher.zwift.com
   ```
3. **Обновите cacert.pem**:
откройте директорию с файлом cert-zwift-com.pem
если вы скачали cert-zwift-com.pem в загрузки тогда
<img width="2148" height="966" alt="image" src="https://github.com/user-attachments/assets/2f08f2d1-f7d5-43cc-93d6-49ff152e5c2e" />

```bash
   cd Downloads
```
и введите
   ```bash
   sed -n '29,53p' cert-zwift-com.pem >> ~/Library/Application\ Support/Zwift/data/cacert.pem
   ```

#### Android
1. **Установите приложения**:
   - [reZObb.apk]
   - [Virtual Hosts]
2. **Создайте файл hosts.txt** с адресами серверов
3. **Отключите Private DNS** в настройках Android
4. **Запустите Virtual Hosts** и выберите созданный файл

## 📂 **Где хранятся данные Zwift на разных ОС**

### **🪟 Windows:**
```
C:\Users\[ИмяПользователя]\Documents\Zwift\Activities\
```
![telegram-cloud-photo-size-2-5233320803418442732-y](https://github.com/user-attachments/assets/54907554-02d3-49b5-856a-4c1ef01f6c38)

- **Найти:** Проводник → Документы → Zwift → Activities
- **Файлы:** `.fit`, `.tcx` - тренировки и активности

### **🍎 macOS:**
```
/Users/[ИмяПользователя]/Documents/Zwift/Activities/
```
<img width="2720" height="1144" alt="image" src="https://github.com/user-attachments/assets/6b919d9d-e207-447f-b42f-daf8ee876274" />

- **Найти:** Finder → Документы → Zwift → Activities  
- **Файлы:** `.fit`, `.tcx` - тренировки и активности

### **📱 Android:**
```
/storage/emulated/0/Android/data/com.zwift.zwift/files/activities/
```
- **Через файловый менеджер** или приложение для резервного копирования

### **💡 Советы:**
- Файлы могут быть в поддиректориях по датам: `Activities/2024/11/`
- FIT файлы - бинарный формат с GPS/пульсом/мощностью
- TCX файлы - XML формат для других приложений
- Регулярно делайте бэкап этих файлов!

**🚴‍♂️ Ваши тренировки - это ваша история спорта!** 💾📊

### Шаг 4: Первый запуск

1. **Запустите Zwift** обычным способом
2. **Откроется лаунчер reZwift** в браузере
   <img width="981" height="555" alt="telegram-cloud-document-2-5226687535207451898" src="https://github.com/user-attachments/assets/b905f90d-facf-40d4-96ab-05cbb5d5d4ae" />

4. **Создайте аккаунт**:
   - Email: `user@rezwift.local` (или любой)
   - Пароль: любой пароль
  <img width="742" height="557" alt="telegram-cloud-document-2-5226687535207451899" src="https://github.com/user-attachments/assets/602d942c-a22c-4c88-8f74-feb39e8f504b" />
  
5. **Выберите карту и маршрут**
6. **Нажмите "Запустить Zwift"**

## ⚙️ Настройки и интеграции

### Подключение Garmin Connect

**Работает в России без VPN!**

1. В лаунчере нажмите **"Настройки"**
   
   <img width="947" height="429" alt="telegram-cloud-document-2-5226687535207451911" src="https://github.com/user-attachments/assets/104ae9a2-4e02-4b05-af20-ad5ed552e5ae" />

3. Перейдите на вкладку **"Garmin"**

  <img width="942" height="554" alt="telegram-cloud-document-2-5226687535207451912" src="https://github.com/user-attachments/assets/5c34ea37-89d8-4e41-abb9-16474c5679ef" />

5. Введите email и пароль от Garmin Connect
  
6. Нажмите **"Сохранить"**

Тренировки будут автоматически загружаться после завершения.

### Подключение Intervals.icu

1. В настройках лаунчера выберите **"Intervals"**
   
   <img width="947" height="429" alt="telegram-cloud-document-2-5226687535207451911" src="https://github.com/user-attachments/assets/d3ad0491-d89b-4d7e-8c79-8c9f23a6f799" />

3. Скопируйте **Athlete ID** и **API Key** из [настроек Intervals.icu](https://intervals.icu/settings)
<img width="919" height="550" alt="telegram-cloud-document-2-5226687535207451913" src="https://github.com/user-attachments/assets/686a9ee7-fe19-449b-ad92-e18f300d8948" />

4. Вставьте в соответствующие поля

## 🌍 Доступные карты

Все карты Zwift доступны в любое время:

![telegram-cloud-photo-size-2-5213322868752584622-y](https://github.com/user-attachments/assets/e09f064e-d91a-4841-8669-1a561b270faf)

- **Watopia** - тропический остров
- **London** - улицы Лондона
- **Yorkshire** - сельская местность
- **Innsbruck** - альпийские горы
- **New York** - улицы Манхэттена
- **Paris** - набережные Сены
- **Makuri Islands** - вулканический архипелаг
- **Scotland** - шотландские горы

## 🎮 Возможности reZwift

### Основные функции
- ✅ **Свободный выбор карт** - любые маршруты в любое время
- ✅ **Без подписки** - полный функционал бесплатно
- ✅ **Призраки** - соревнования с предыдущими тренировками
- ✅ **Боты** - AI-соперники на маршрутах
- ✅ **Закладки** - сохранение позиций для продолжения тренировок
- ✅ **Мультиплеер** - тренировки с друзьями
- ✅ **Лидерборды** - рекорды и достижения

### Интеграции
- ✅ **Garmin Connect** - автоматическая загрузка без VPN
- ✅ **Strava** - синхронизация активностей
- ✅ **Intervals.icu** - детальный анализ тренировок
- ✅ **Zwift Companion** - мобильное приложение

### Дополнительные возможности
- ✅ **Кастомизация снаряжения** - разблокировка всего оборудования
- ✅ **RoboPacers** - динамические боты с имитацией мощности
- ✅ **Все достижения и XP** - полный прогресс сохраняется

## 💬 Команды в игре

- `.regroup` - перегруппировать призраков
- `.bookmark <name>` - сохранить закладку

## ❓ FAQ - Часто задаваемые вопросы

### 🔰 Основные вопросы

****Что такое reZwift?**
> reZwift — это альтернативный сервер для Zwift, позволяющий использовать игру без подписки, с выбором любых карт и интеграцией с Garmin/Strava без VPN.

**Нужна ли подписка Zwift?**
> Нет! reZwift работает полностью автономно. Вам нужен только установленный клиент Zwift.

**Безопасно ли использовать reZwift?**
> Да, безопасно. reZwift не взаимодействует с официальными серверами Zwift и не использует ваш реальный аккаунт.

**Работает ли reZwift в России без VPN?**
> Да! Игра работает без VPN, а загрузка тренировок в Garmin Connect и Strava тоже происходит без VPN.

### 🤬 Ошибки и их решение

- **Не отображаются шрифты**
![telegram-cloud-photo-size-2-5222349348115517064-w](https://github.com/user-attachments/assets/a53ca104-d5ce-426d-8f77-e8a3d33f4d06)
> Действительно это иногда встречается по не совсем известным причинам.
Испрвить это можно 1. Закрытием лаунчера звифт 2. Его повторным запуском, а иногда так же помогат перезагрузка устройства.

- **Брандмауэр Защитника Windows заблокировал некоторые
функции этого приложения**
![telegram-cloud-photo-size-2-5222349348115517055-w](https://github.com/user-attachments/assets/dcfc2db5-ddff-4473-8aee-d9ad54432167)
> Для корректной работы рекомендовано выбрать пункт "Разрешить" **но** при этом выбрав в частных и общественных сетях.

- **Bad Request**
![telegram-cloud-photo-size-2-5226683528462929043-y](https://github.com/user-attachments/assets/68a87aad-88aa-454a-aa1a-0468f8e40fe6)
> Немедленно написать в телеграмм канал, после клика по какому пункту это произошло.

### 💾 Сохранение данных

**Сохраняются ли тренировки?**
> Да! Сохраняются все тренировки, прогресс, уровень, достижения, личные рекорды и разблокированное снаряжение.

**Как загрузить тренировки в Garmin/Strava?**
> В настройках лаунчера введите логин/пароль от Garmin Connect. Тренировки загружаются автоматически после завершения.

### 🌍 Карты и маршруты

**Какие карты доступны?**
> Все официальные карты Zwift: Watopia, London, Yorkshire, Innsbruck, New York, Paris, Makuri Islands, Scotland.

**Что такое "призраки"?**
> Это ваши предыдущие тренировки. Включаются в лаунчере, позволяют соревноваться с собой.

**Что такое "боты"?**
> AI-райдеры, которые катаются вместе с вами. Добавляют атмосферу и мотивацию.

### 👥 Мультиплеер

**Можно ли кататься с друзьями?**
> Да! Если друзья тоже используют reZwift и подключены к тому же серверу.

**Работают ли датчики (пульсометр, мощность)?**
> Да! Все ANT+ и Bluetooth устройства работают как обычно.

### 🔧 Проблемы с подключением

**Не могу подключиться к reZwift?**
> 1. Убедитесь, что скрипт настройки был запущен от имени администратора
> 2. Полностью закройте Zwift (включая иконку в трее)
> 3. Перезагрузите компьютер
> 4. Попробуйте снова

**Как вернуться к официальному Zwift?**
> Обратитесь к администратору сервера для помощи с возвратом к официальным серверам Zwift.

### 🎮 Игровой процесс

**Сохраняется ли уровень и опыт?**
> Да! Все XP, уровни, дропы и достижения сохраняются.

**Можно ли разблокировать всё снаряжение?**
> Да, эта функция есть. Обратитесь к администратору сервера.

**Работают ли лидерборды?**
> Да! Все личные рекорды и результаты сохраняются.

## 🆘 Поддержка

### Сообщество
- **Telegram канал**: [@reZwift](https://t.me/rezwift)
- **Обновления**: Следите за новостями в Telegram

**Ride On!** 🚴‍♂️🚴‍♀️
![telegram-cloud-photo-size-2-5213322868752584623-y](https://github.com/user-attachments/assets/de75347d-7715-4175-b90c-cd7ca8b6abe1)

---

*Это руководство создано сообществом reZwift для помощи пользователям.*

<img width="792" height="443" alt="image" src="https://github.com/user-attachments/assets/a55fcd5e-a460-4259-ab6b-049f21aeaed1" />
<img width="581" height="573" alt="image" src="https://github.com/user-attachments/assets/838f7022-d077-4452-bec0-d6c100942c36" />
