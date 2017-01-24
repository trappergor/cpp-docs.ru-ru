---
title: "Безопасные библиотеки: стандартная библиотека C++ | Microsoft Docs"
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
  - "_SCL_SECURE_NO_DEPRECATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Безопасные библиотеки"
  - "Безопасные библиотеки, стандартная библиотека C++"
  - "Безопасная стандартная библиотека C++"
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Безопасные библиотеки: стандартная библиотека C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В библиотеки, входящие в состав Visual C\+\+ \(включая стандартную библиотеку C\+\+\), были внесены различные улучшения, чтобы сделать их более безопасными.  
  
 В стандартной библиотеке C\+\+ несколько методов оказались потенциально небезопасными, поскольку могли привести к переполнению буфера или другим дефектам кода. Использовать эти методы не рекомендуется; вместо них созданы новые, более безопасные методы. Эти новые методы оканчиваются на `_s`.  
  
 Также были внесены некоторые улучшения для повышения безопасности итераторов и алгоритмов. Дополнительные сведения см. в разделах [Проверяемые итераторы](../standard-library/checked-iterators.md), [Поддержка отладки итераторов](../standard-library/debug-iterator-support.md) и [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Заметки  
 В следующей таблице перечислены потенциально небезопасные методы стандартной библиотеки C\+\+, а также их более безопасные эквиваленты:  
  
|Потенциально небезопасный метод|Более безопасный эквивалент|  
|-------------------------------------|---------------------------------|  
|[basic\_string::copy](../Topic/basic_string::copy.md)|[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)|  
|[char\_traits::copy](../Topic/char_traits::copy.md)|[char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)|  
  
 При вызове любого из перечисленных выше потенциально небезопасных методов или при неправильном использовании итераторов компилятор создает [Предупреждение компилятора \(уровень 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Сведения о том, как отключить эти предупреждения, см. в разделе [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## Содержание  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Проверяемые итераторы](../standard-library/checked-iterators.md)  
  
 [Поддержка отладки итераторов](../standard-library/debug-iterator-support.md)  
  
## См. также  
 [Обзор STL](../standard-library/cpp-standard-library-overview.md)