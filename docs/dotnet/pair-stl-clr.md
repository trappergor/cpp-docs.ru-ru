---
title: "pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair - класс [STL/CLR]"
ms.assetid: 3326b4d9-a52a-49e5-8103-9aa5e8b352de
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона описание объекта, который создает экземпляры пара значений.  
  
## Синтаксис  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### Параметры  
 Value1  
 Тип первого создаватього программу\-оболочку значение.  
  
 Value2  
 Тип второго создаватього программу\-оболочку значение.  
  
## Члены  
  
|Определение типа|Описание|  
|----------------------|--------------|  
|[pair::first\_type](../dotnet/pair-first-type-stl-clr.md)|Тип первого создаватього программу\-оболочку значение.|  
|[pair::second\_type](../dotnet/pair-second-type-stl-clr.md)|Тип второго создаватього программу\-оболочку значение.|  
  
|Объект\-член|Описание|  
|------------------|--------------|  
|[pair::first](../dotnet/pair-first-stl-clr.md)|Первое, хранящееся значение.|  
|[pair::second](../dotnet/pair-second-stl-clr.md)|Второе сохраненного значения.|  
  
|Функция Member|Описание|  
|--------------------|--------------|  
|[pair::pair](../dotnet/pair-pair-stl-clr.md)|Создает объект пар.|  
|[pair::swap](../Topic/pair::swap%20\(STL-CLR\).md)|Замена содержимого 2 пар.|  
  
|Оператор|Описание|  
|--------------|--------------|  
|[pair::operator\=](../dotnet/pair-operator-assign-stl-clr.md)|Заменяет, хранящиеся в паре значений.|  
  
## Заметки  
 Объект содержит пары значений.  Используется этот класс шаблона, чтобы объединить значения 2 на один объект.  Обратите внимание, что `cliext::pair` \(описанный здесь\) хранит только управляемые типы; для хранения пар неуправляемых типов используйте объявлен как `std::pair`, в `<utility>`.  
  
## Требования  
 **Заголовок:**\<cliext\/utility\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [make\_pair](../dotnet/make-pair-stl-clr.md)