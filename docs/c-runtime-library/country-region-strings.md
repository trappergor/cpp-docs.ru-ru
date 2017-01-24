---
title: "Строки стран или регионов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.strings"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "строки страны и региона"
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Строки стран или регионов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Строки страны и региона можно объединять со строкой с названием языка для создания спецификации языкового стандарта для функций `setlocale`, `_wsetlocale`, `_create_locale` и `_wcreate_locale`. Список названий стран и регионов, поддерживаемых различными версиями операционной системы Windows, см. в разделе [National Language Support \(NLS\) API Reference](http://msdn.microsoft.com/goglobal/bb896001.aspx). В списках строка страны может быть любым значением страны из столбца **Locale — Language Country\/Region** или любой из аббревиатур из столбца **Country or Region name abbreviation**.  
  
 Реализация библиотеки времени выполнения C также поддерживает следующие дополнительные строки и аббревиатуры стран и регионов:  
  
|Строка страны или региона|Сокращение|Соответствующее название языкового стандарта|  
|-------------------------------|----------------|--------------------------------------------------|  
|america|USA|ru\-RU|  
|britain|GBR|en\-GB|  
|china|CHN|zh\-CN|  
|czech|CZE|cs\-CZ|  
|england|GBR|en\-GB|  
|great britain|GBR|en\-GB|  
|holland|NLD|nl\-NL|  
|hong\-kong|HKG|zh\-HK|  
|new\-zealand|NZL|en\-NZ|  
|nz|NZL|en\-NZ|  
|pr china|CHN|zh\-CN|  
|pr\-china|CHN|zh\-CN|  
|puerto\-rico|PRI|es\-PR|  
|slovak|SVK|sk\-SK|  
|south africa|ZAF|af\-ZA|  
|south korea|KOR|ko\-KR|  
|south\-africa|ZAF|af\-ZA|  
|south\-korea|KOR|ko\-KR|  
|trinidad & tobago|TTO|en\-TT|  
|uk|GBR|en\-GB|  
|united\-kingdom|GBR|en\-GB|  
|united\-states|USA|ru\-RU|  
|us|USA|ru\-RU|  
  
## См. также  
 [Строки имени языкового стандарта, языка и страны и региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Строки языка](../c-runtime-library/language-strings.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)