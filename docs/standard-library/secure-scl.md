---
title: "_SECURE_SCL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SECURE_SCL"
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _SECURE_SCL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет, включена ли [Проверяемые итераторы](../standard-library/checked-iterators.md).  Если определен как 1, небезопасное использование итераторов вызовет ошибку во время выполнения и программы.  Если определен как 0, установленные итераторы запрещены.  В режиме отладки, значение по умолчанию для **\_SECURE\_SCL** 1. это означает, что установленные итераторы включены.  В режиме выпуска, значение по умолчанию для `_SECURE_SCL` 0.  
  
> [!IMPORTANT]
>  Используйте `_ITERATOR_DEBUG_LEVEL` к элементу управления `_SECURE_SCL`.  Для получения дополнительной информации см. [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Заметки  
 Чтобы позволить проверить итераторы, установите **\_SECURE\_SCL** до 1:  
  
```  
#define _SECURE_SCL 1  
```  
  
 Чтобы отключить проверку итераторы, установите **\_SECURE\_SCL** до 0:  
  
```  
#define _SECURE_SCL 0  
```  
  
 Дополнительные сведения об отключении предупреждения о помеченных итераторах см. в разделе [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## См. также  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)   
 [Проверяемые итераторы](../standard-library/checked-iterators.md)   
 [Поддержка отладки итераторов](../standard-library/debug-iterator-support.md)   
 [Безопасные библиотеки: стандартная библиотека C\+\+](../standard-library/safe-libraries-cpp-standard-library.md)