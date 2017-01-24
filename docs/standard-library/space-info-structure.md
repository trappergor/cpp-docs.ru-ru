---
title: "Структура space_info | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::space_info"
dev_langs: 
  - "C++"
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: 13
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура space_info
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Содержит сведения о томе.  
  
## Синтаксис  
  
```  
struct space_info;  
```  
  
## Члены  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|`unsigned long long available`|Представляет число байтов, доступных для представления данных в томе.|  
|`unsigned long long capacity`|Представляет общее число байтов, которое может представлять том.|  
|`unsigned long long free`|Представляет число байтов, не используемых для представления данных в томе.|  
  
## Требования  
 **Заголовок:** filesystem  
  
 **Пространство имен:** std::tr2::sys  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)   
 [Функция space](http://msdn.microsoft.com/ru-ru/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Навигация по файловой системе \(C\+\+\)](../standard-library/file-system-navigation.md)