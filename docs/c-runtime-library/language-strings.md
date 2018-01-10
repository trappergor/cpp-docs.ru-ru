---
title: "Строки языка | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.strings
dev_langs: C++
helpviewer_keywords: language strings
ms.assetid: bbee63b1-af0b-4e44-9eaf-dd3e265c05fd
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 85f0c9b06ae85128209f06d95375e09043b3f9c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="language-strings"></a>Language Strings
Функции `setlocale` и `_create_locale` могут использовать поддерживаемые языки API многоязыковой поддержки Windows для операционных систем, которые не используют кодовую страницу Юникода. Список языков, поддерживаемых в разных версиях операционных систем, вы найдете в [документации по API многоязыковой поддержке (NLS)](https://www.microsoft.com/resources/msdn/goglobal/default.mspx). Строка языка может принимать любое из значений, перечисленных в столбцах **Язык** и **Сокращение названия языка** списка поддерживаемых языков. Дополнительные сведения о языковой поддержке по версии операционной системы см. в [приложении A: поведение продукта](http://msdn.microsoft.com/goglobal/bb896001.aspx) в статье [MS-LCID]: Windows Language Code Identifier (LCID) Reference ([MS-LCID]: справочник по коду языка Windows).   
  
Реализация библиотеки времени выполнения C также поддерживает эти строки языка:  
  
|Строка языка|Соответствующее название языкового стандарта|  
|---------------------|----------------------------|  
|американский|ru-RU|  
|американский английский|ru-RU|  
|американский — английский|ru-RU|  
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
|английский — американский|ru-RU|  
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
|английский — us|ru-RU|  
|английский — США|ru-RU|  
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
|us|ru-RU|  
|США|ru-RU|  
  
## <a name="see-also"></a>См. также  
 [Строки имени языкового стандарта, языка и страны и региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Строки страны и региона](../c-runtime-library/country-region-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)