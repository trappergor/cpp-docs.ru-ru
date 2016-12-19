---
title: "Класс mutex (STL) | Microsoft Docs"
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
  - "mutex/std::mutex"
dev_langs: 
  - "C++"
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс mutex (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет *тип мьютексов*.  Объекты этого типа можно использовать для обеспечения взаимное исключение внутри программы.  
  
## Синтаксис  
  
```  
class mutex;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор mutex::mutex \(STL\)](../Topic/mutex::mutex%20Constructor%20\(STL\).md)|Создает объект `mutex`.|  
|[Деструктор mutex::~mutex \(STL\)](../Topic/mutex::~mutex%20Destructor%20\(STL\).md)|Выпуски все ресурсы, используемые объектом `mutex`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод mutex::lock \(STL\)](../Topic/mutex::lock%20Method%20\(STL\).md)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[Метод mutex::native\_handle \(STL\)](../Topic/mutex::native_handle%20Method%20\(STL\).md)|Возвращает тип для предоставления, представляющий дескриптор мьютекса.|  
|[Метод mutex::try\_lock \(STL\)](../Topic/mutex::try_lock%20Method%20\(STL\).md)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[Метод mutex::unlock \(STL\)](../Topic/mutex::unlock%20Method%20\(STL\).md)|Освобождает права владения объектом `mutex`.|  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)