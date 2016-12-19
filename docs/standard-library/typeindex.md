---
title: "&lt;typeindex&gt; | Microsoft Docs"
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
  - "<typeindex>"
dev_langs: 
  - "C++"
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;typeindex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Включите стандартный заголовок \<typeindex\> для определения класса и функции, которые поддерживают индексирование объектов класса [type\_information](../cpp/type-info-class.md).  
  
## Синтаксис  
  
```cpp  
#include <typeindex>  
```  
  
## Заметки  
 [Структура hash](../standard-library/hash-structure.md) определяет `hash function`, подходит для сопоставления значений типа [type\_index](../standard-library/type-index-class.md) на распределение значений индекса.  
  
 Класс `type_index` создания указатель на объект `type_info` в помогает при индексировании.  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)