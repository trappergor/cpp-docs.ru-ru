---
title: "Строки страны и региона | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.strings
dev_langs: C++
helpviewer_keywords: country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c250e47688e5fbcb32779d58dd8fe8973cdc96c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="countryregion-strings"></a>Country/Region Strings
Строки страны и региона можно объединять со строкой с названием языка для создания спецификации языкового стандарта для функций `setlocale`, `_wsetlocale`, `_create_locale`и `_wcreate_locale` . Список названий стран и регионов, поддерживаемых различными версиями операционной системы Windows, см. в разделе[National Language Support (NLS) API Reference](https://www.microsoft.com/resources/msdn/goglobal/default.mspx) (Справочник по API многоязыковой поддержки (NLS)). В списках строка страны или региона может приобретать любое значение страны из столбца **Языковые стандарты — Language Country/Region** (Страна или регион языка) или любой из аббревиатур из столбца **Country or Region name abbreviation** (Аббревиатура названия страны или региона). Дополнительные сведения о поддержке языков по версии операционной системы Windows см. в [приложении A: поведение продуктов](http://msdn.microsoft.com/goglobal/bb896001.aspx) в статье [MS-LCID]: Windows Language Code Identifier (LCID) Reference ([MS-LCID]: справочник по коду языка Windows).  
  
 Реализация библиотеки времени выполнения C также поддерживает следующие дополнительные строки и аббревиатуры стран и регионов:  
  
|Строка страны или региона|Сокращение|Соответствующее название языкового стандарта|  
|----------------------------|------------------|----------------------------|  
|america|USA|ru-RU|  
|britain|GBR|en-GB|  
|china|CHN|zh-CN|  
|czech|CZE|cs-CZ|  
|england|GBR|en-GB|  
|great britain|GBR|en-GB|  
|holland|NLD|nl-NL|  
|hong-kong|HKG|zh-HK|  
|new-zealand|NZL|en-NZ|  
|nz|NZL|en-NZ|  
|pr china|CHN|zh-CN|  
|pr-china|CHN|zh-CN|  
|puerto-rico|PRI|es-PR|  
|slovak|SVK|sk-SK|  
|south africa|ZAF|af-ZA|  
|south korea|KOR|ko-KR|  
|south-africa|ZAF|af-ZA|  
|south-korea|KOR|ko-KR|  
|trinidad & tobago|TTO|en-TT|  
|uk|GBR|en-GB|  
|united-kingdom|GBR|en-GB|  
|united-states|USA|ru-RU|  
|us|USA|ru-RU|  
  
## <a name="see-also"></a>См. также  
 [Строки имени языкового стандарта, языка и страны и региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Строки языка](../c-runtime-library/language-strings.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)