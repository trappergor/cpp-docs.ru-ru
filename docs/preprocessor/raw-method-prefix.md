---
title: "raw_method_prefix | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_method_prefix"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_method_prefix - атрибут"
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# raw_method_prefix
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Указывает другой префикс, чтобы избежать конфликтов имен.  
  
## Синтаксис  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### Параметры  
 `Prefix`  
 Необходимый префикс.  
  
## Заметки  
 Низкоуровневые свойства и методы предоставляются функциями\-членами, имя которых содержит префикс по умолчанию **raw\_**, чтобы избежать конфликтов имен с высокоуровневыми функциями\-членами для обработки ошибок.  
  
> [!NOTE]
>  Влияние атрибута `raw_method_prefix` не изменится из\-за присутствия атрибута [raw\_interfaces\_only](#_predir_raw_interfaces_only).  `raw_method_prefix` всегда имеет приоритет над `raw_interfaces_only` в определении префикса.  Если оба атрибута используются в одном и том же операторе `#import`, используется префикс, определяемый атрибутом `raw_method_prefix`.  
  
 **Завершение блока, относящегося только к языку C\+\+**  
  
## См. также  
 [Атрибуты \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md)