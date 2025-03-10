# ASM-Tourism
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ASM - تنظيم رحلات سياحية</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f8ff; /* لون خلفية أزرق فاتح */
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #00008b; /* لون أزرق داكن */
        }
        form {
            display: inline-block;
            text-align: right;
            background: #ffffff; /* لون خلفية أبيض */
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 500px;
        }
        label {
            display: block;
            margin: 10px 0 5px;
            font-weight: bold;
            color: #000000; /* لون أسود */
        }
        input, select, textarea, button {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #00008b; /* لون أزرق داكن */
            border-radius: 4px;
            font-size: 16px;
            color: #000000; /* لون أسود */
        }
        button {
            background-color: #00008b; /* لون أزرق داكن */
            color: white;
            cursor: pointer;
            border: none;
        }
        button:hover {
            background-color: #0000cd; /* لون أزرق متوسط */
        }
        .language-switcher {
            margin-bottom: 20px;
        }
        .language-switcher button {
            width: auto;
            margin: 5px;
            padding: 5px 10px;
            font-size: 14px;
            background-color: #00008b; /* لون أزرق داكن */
            color: white;
            border: none;
            border-radius: 4px;
        }
        .language-switcher button:hover {
            background-color: #0000cd; /* لون أزرق متوسط */
        }
    </style>
</head>
<body>
    <div class="language-switcher">
        <button onclick="changeLanguage('ar')">العربية</button>
        <button onclick="changeLanguage('en')">English</button>
        <button onclick="changeLanguage('fr')">Français</button>
    </div>

    <h1 id="title">ASM - تنظيم رحلات سياحية</h1>

    <form id="tripForm">
        <label for="name" id="nameLabel">الاسم:</label>
        <input type="text" id="name" required>

        <label for="phone" id="phoneLabel">رقم الهاتف:</label>
        <input type="tel" id="phone" required>

        <label for="email" id="emailLabel">الإيميل:</label>
        <input type="email" id="email" required>

        <label for="language" id="languageLabel">اللغة:</label>
        <select id="language" required>
            <option value="ar">العربية</option>
            <option value="en">English</option>
            <option value="fr">Français</option>
        </select>

        <button type="submit" id="submitButton">تأكيد الرحلة</button>
    </form>

    <script>
        // بيانات اللغة
        const translations = {
            ar: {
                title: "ASM - تنظيم رحلات سياحية",
                nameLabel: "الاسم:",
                phoneLabel: "رقم الهاتف:",
                emailLabel: "الإيميل:",
                languageLabel: "اللغة:",
                submitButton: "تأكيد الرحلة"
            },
            en: {
                title: "ASM - Tourism Trips",
                nameLabel: "Name:",
                phoneLabel: "Phone:",
                emailLabel: "Email:",
                languageLabel: "Language:",
                submitButton: "Confirm Trip"
            },
            fr: {
                title: "ASM - Organisation de voyages touristiques",
                nameLabel: "Nom:",
                phoneLabel: "Téléphone:",
                emailLabel: "Email:",
                languageLabel: "Langue:",
                submitButton: "Confirmer le voyage"
            }
        };

        // تغيير اللغة
        function changeLanguage(lang) {
            document.getElementById("title").innerText = translations[lang].title;
            document.getElementById("nameLabel").innerText = translations[lang].nameLabel;
            document.getElementById("phoneLabel").innerText = translations[lang].phoneLabel;
            document.getElementById("emailLabel").innerText = translations[lang].emailLabel;
            document.getElementById("languageLabel").innerText = translations[lang].languageLabel;
            document.getElementById("submitButton").innerText = translations[lang].submitButton;
        }

        // حفظ البيانات
        document.getElementById("tripForm").addEventListener("submit", function(event) {
            event.preventDefault();
            const tripData = {
                name: document.getElementById("name").value,
                phone: document.getElementById("phone").value,
                email: document.getElementById("email").value,
                language: document.getElementById("language").value
            };
            localStorage.setItem("tripData", JSON.stringify(tripData)); // حفظ البيانات
            alert("تم تأكيد الرحلة بنجاح!");
        });
    </script>
</body>
</html>
