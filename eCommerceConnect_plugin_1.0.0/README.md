# OpenCart 4 Payment Module — eCommerceConnect

## 🇺🇦 Інструкція українською

### Вимоги
- **OpenCart:** >= 4.0.0
- **PHP:** >= 8.0
- **MySQL/MariaDB**
- **cURL** (увімкнено на сервері)
- SSL-сертифікат для продакшн сайту

### Установка
1. Скопіюйте папку `ecommerceconnect` у директорію:
   ```
   /extension/ecommerceconnect
   ```

2. Увійдіть в **адмін-панель OpenCart**:
   - Перейдіть до **Extensions → Extensions**
   - У випадаючому меню оберіть **Payments**
   - Знайдіть **eCommerceConnect Payment** і натисніть **Install**

3. Після інсталяції натисніть **Edit** для відкриття налаштувань.

### Налаштування
- **Merchant ID** — ідентифікатор вашого мерчанта
- **Terminal ID** — ідентифікатор терміналу
- **Private Key (PEM)** — приватний ключ для підпису
- **Contract Currency** — основна валюта за контрактом (наприклад, UAH)
- **Alternative Currency** — відображувана валюта (USD або EUR)
- **Pre-authorization** — вмикає режим холду коштів з подальшим Capture (після холду в замовленні з’явиться вкладка для часткового/повного списання)

### Webhook

URL для отримання повідомлень від платіжного сервісу:

```https://example.com/index.php?route=extension/ecommerceconnect/payment/ecommerceconnect.callback```

Webhook автоматично:
- Перевіряє підпис відповіді
- Оновлює статус замовлення
- Зберігає технічну інформацію про транзакцію

### Особливості
- Збереження **UPC Token** користувача у прихованих полях (доступно лише адміну)
- Підтримка **Pre-authorization / Capture**
- Облік багатовалютності: завжди використовується контрактна валюта + альтернативна (USD/EUR)

---

## 🇬🇧 English Instructions

### Requirements
- **OpenCart:** >= 4.0.0
- **PHP:** >= 8.0
- **MySQL/MariaDB**
- **cURL** enabled
- SSL certificate for production site

### Installation
1. Copy the `ecommerceconnect` folder into:
   ```
   /extension/ecommerceconnect
   ```

2. Log in to **OpenCart Admin Panel**:
   - Go to **Extensions → Extensions**
   - Select **Payments** from the dropdown
   - Find **eCommerceConnect Payment** and click **Install**

3. After installation click **Edit** to configure settings.

### Configuration
- **Merchant ID** — your merchant identifier
- **Terminal ID** — terminal identifier
- **Private Key (PEM)** — private signing key
- **Contract Currency** — base currency of your contract (e.g., UAH)
- **Alternative Currency** — display currency (USD or EUR)
- **Pre-authorization** — enables funds hold with later Capture (after hold, an additional tab appears in the order to capture partial/full funds)

### Webhook
Webhook URL for receiving payment notifications:

```https://example.com/index.php?route=extension/ecommerceconnect/payment/ecommerceconnect.callback```

The webhook automatically:
- Validates response signature
- Updates order status
- Stores technical transaction details

### Features
- Stores **UPC User Token** in hidden fields (admin-only access)
- Supports **Pre-authorization / Capture**
- Multi-currency support: always uses contract currency + alternative (USD/EUR)
