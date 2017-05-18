---
title: "Строки страны и региона | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.strings
dev_langs:
- C++
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 708651f59ceff638482264e3fc57228e8a1822b2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="countryregion-strings"></a>Country/Region Strings
Строки страны и региона можно объединять со строкой с названием языка для создания спецификации языкового стандарта для функций `setlocale`, `_wsetlocale`, `_create_locale`и `_wcreate_locale` . Список названий стран и регионов, поддерживаемых различными версиями операционной системы Windows, см. в разделе [National Language Support (NLS) API Reference](http://msdn.microsoft.com/goglobal/bb896001.aspx). В списках строка страны может быть любым значением страны из столбца **Locale — Language Country/Region** или любой из аббревиатур из столбца **Country or Region name abbreviation**.  
  
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
