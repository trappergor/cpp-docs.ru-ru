---
title: "&lt;limits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<limits>"
  - "std::<limits>"
  - "limits/std::<limits>"
  - "<limits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "limits - заголовок"
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# &lt;limits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс шаблона `numeric_limits` и два перечисления, касающиеся представления значений с плавающей запятой и округления.  
  
## Синтаксис  
  
```  
  
#include <limits>  
  
```  
  
## Заметки  
 Явные специализации класса `numeric_limits` описывают множество свойств базовых типов, включая включая символьные типа, целочисленные типы, типы с плавающей запятой и `bool`, определяемые реализацией, а не фиксированными правилами языка C\+\+.  Свойства, описанные в \<ограничении\>, включают точность, минимальный и максимальный размер представления, округление и сообщения об ошибках типа.  
  
### Перечисления  
  
|||  
|-|-|  
|[float\_denorm\_style](../Topic/float_denorm_style.md)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:|  
|[float\_round\_style](../Topic/float_round_style.md)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|  
  
### Классы  
  
|||  
|-|-|  
|[Класс numeric\_limits](../standard-library/numeric-limits-class.md)|Класс шаблона описывает арифметические свойства встроенных числовых типов.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)