

## **Language Support using i18next (React)**

1. **Install Packages**

```bash
npm install i18next react-i18next
```

2. **Create Translation Files**
   `public/locales/en/translation.json`
   `public/locales/bn/translation.json`

Example:

```json
{ "welcome": "Welcome" } 
{ "welcome": "স্বাগতম" } 
```

3. **Initialize i18next** (`src/i18n.js`)

```javascript
import i18n from 'i18next';
import { initReactI18next } from 'react-i18next';

i18n.use(initReactI18next).init({
  resources: { en: { translation: require('../public/locales/en/translation.json') }, bn: { translation: require('../public/locales/bn/translation.json') } },
  lng: 'en',
  fallbackLng: 'en',
  interpolation: { escapeValue: false }
});
export default i18n;
```

4. **Use in Components**

```javascript
import { useTranslation } from 'react-i18next';
const { t, i18n } = useTranslation();
<h1>{t('welcome')}</h1>
<button onClick={() => i18n.changeLanguage('en')}>English</button>
<button onClick={() => i18n.changeLanguage('bn')}>বাংলা</button>
```

Click button → language changes instantly.
