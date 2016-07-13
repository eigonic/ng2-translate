# ng2-translate

Angular 2 Pipe in TypeScript that is used to translate your app into multi-languages. It is suitable for Inoic 2

## Installation
Just copy the file `eigonic-translate.ts` into your project.

## Usage
Follow these steps to use the module:


1. Import the `eiognic` module into your code.
2. Create languages bundle to have all the translations you have.
3. Initialize the `eigonic.Translator` with the languages bandle and the default language.
4. In the template, use the   `eigonic.Translator` pipe named `translate` to convert the keywords to their translations.
 
### app.component.ts
```javascript
import { Component } from '@angular/core';
import {LangBundle} from './langBundle';
import {eigonic} from './eigonic-translate';

@Component({
  moduleId: module.id,
  selector: 'app-root',
  template: `
  <h1>
  {{title}}
</h1>

<ul>
  <li>{{'HOME'|translate}}</li>
  <li>{{'NOT TRANSLATED'|translate}}</li>
  <li>{{'SETTINGS'|translate}}</li>
</ul>
  `, 
  pipes: [eigonic.Translator]
})
export class AppComponent {
  title = 'eigonic ng2-translate works!';

  constructor() {
    eigonic.Translator.init(LangBundle.MSG, 'ar');
  }
}

```
### langBundle.ts

```javascript

export class LangBundle {
    static MSG: any = {
        "en": {
            HOME: 'Home',
            EXPORT: 'Export',
            REPORTS: 'Reports',
            SETTINGS: 'Settings'
        },
        "ar":
        {
            HOME: 'الرئيسية',
            REPORTS: 'التقارير',
            EXPORT: 'Export',
            PROFILE: 'الملف الشخصي',
            SETTINGS: 'الإعدادات'
        }
    };
}

```
## Default language
Default language is used in case the current language is not set. It's some sort of fallback language.

## Change/ switch language

To change or switch the current language. 

```javascript
    eigonic.Translator.switchLang('en');
```

## License 
It is Apache2 but I personally prefere the [WTFPL](https://en.wikipedia.org/wiki/WTFPL)  
![WTFPL](https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/WTFPL_logo.svg/140px-WTFPL_logo.svg.png "WTFPL logo")

## Feedback
Feel free to ask for anything.
