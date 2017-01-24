---
title: "raw_property_prefixes | Microsoft Docs"
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
  - "raw_property_prefixes"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "raw_property_prefixes - атрибут"
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_property_prefixes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Задает другие префиксы для трех методов свойств.  
  
## Синтаксис  
  
```  
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### Параметры  
 `GetPrefix`  
 Префикс, используемый для методов **propget**.  
  
 `PutPrefix`  
 Префикс, используемый для методов **propput**.  
  
 `PutRefPrefix`  
 Префикс, используемый для методов **propputref**.  
  
## Заметки  
 По умолчанию низкоуровневые методы **propget**, **propput** и **propputref** предоставляются функциями\-членами с именами, содержащими префиксы **get\_**, **put\_** и **putref\_** соответственно.  Эти префиксы совместимы с именами, используемыми в файлах заголовков, которые генерирует MIDL.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)