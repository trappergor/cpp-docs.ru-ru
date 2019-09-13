---
title: Language Strings
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
ms.openlocfilehash: a9e6eaa65516b5b49022526f24e220dec83b2c26
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500076"
---
# <a name="language-strings"></a>Language Strings

Функции [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) и [_create_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md) могут использовать поддерживаемые языки API многоязыковой поддержки Windows для операционных систем, в которых не применяется кодовая страница Юникода. Список языков, поддерживаемых в разных версиях операционных систем, см. в [приложении с описанием поведения продукта](https://msdn.microsoft.com/library/cc233982.aspx) в справочнике по идентификаторам кода языка Windows [MS-LCID]. Строка языка может принимать любое из значений, перечисленных в столбцах **Язык** и **Тег языка** списка поддерживаемых языков. Пример кода для перечисления имен доступных языковых стандартов и связанных значений см. в руководстве по [ многоязыковой поддержке с примером API на основе имени](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-language-strings"></a>Дополнительные поддерживаемые строки языка

Реализация библиотеки времени выполнения C от Майкрософт также поддерживает эти строки языка:

|Строка языка|Соответствующее название языкового стандарта|
|---------------------|----------------------------|
|американский|en-US|
|американский английский|en-US|
|американский — английский|en-US|
|австралийский|en-AU|
|бельгийский|nl-BE|
|канадский|en-CA|
|chh|zh-HK|
|chi|zh-SG|
|китайский|zh|
|китайский — Гонконг|zh-HK|
|китайский — упрощенное письмо|zh-CN|
|китайский — Сингапур|zh-SG|
|китайский — традиционный|zh-TW|
|голландский — бельгийский|nl-BE|
|английский — американский|en-US|
|английский — aus|en-AU|
|английский — Белиз|en-BZ|
|английский — can|en-CA|
|английский — Карибские острова|en-029|
|английский — ire|en-IE|
|английский — Ямайка|en-JM|
|английский — nz|en-NZ|
|английский — Южная Африка|en-ZA|
|английский — Тринидад и Тобаго|en-TT|
|английский — uk|en-GB|
|английский — us|en-US|
|английский — США|en-US|
|французский — бельгийский|fr-BE|
|французский — канадский|fr-CA|
|французский — Люксембург|fr-LU|
|французский — швейцарский|fr-CH|
|немецкий — австрийский|de-AT|
|немецкий — Лихтенштейн|de-LI|
|немецкий — Люксембург|de-LU|
|немецкий — швейцарский|de-CH|
|ирландский — английский|en-IE|
|итальянский — швейцарский|it-CH|
|норвежский|Нет|
|норвежский — букмол|nb-NO|
|норвежский — нюнорск|nn-NO|
|португальский — бразильский|pt-BR|
|испанский — Аргентина|es-AR|
|испанский — Боливия|es-BO|
|испанский — Чили|es-CL|
|испанский — Колумбия|es-CO|
|испанский — Коста-Рика|es-CR|
|испанский — Доминиканская Республика|es-DO|
|испанский — Эквадор|es-EC|
|испанский — Эль-Сальвадор|es-SV|
|испанский — Гватемала|es-GT|
|испанский — Гондурас|es-HN|
|испанский — мексиканский|es-MX|
|испанский — современный|es-ES|
|испанский — Никарагуа|es-NI|
|испанский — Панама|es-PA|
|испанский — Парагвай|es-PY|
|испанский — Перу|es-PE|
|испанский — Пуэрто-Рико|es-PR|
|испанский — Уругвай|es-UY|
|испанский — Венесуэла|es-VE|
|шведский — Финляндия|sv-FI|
|швейцарский|de-CH|
|uk|en-GB|
|us|en-US|
|США|en-US|

## <a name="see-also"></a>См. также

[Сведения о строках имени языкового стандарта, языка, а также страны или региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Country/Region Strings](../c-runtime-library/country-region-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
