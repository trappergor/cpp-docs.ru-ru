---
title: "__RTDynamicCast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__RTDynamicCast"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__RTDynamicCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__RTDynamicCast"
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# __RTDynamicCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализация оператора [dynamic\_cast](../cpp/dynamic-cast-operator.md) в среде выполнения.  
  
## Синтаксис  
  
```cpp  
PVOID __RTDynamicCast (  
   PVOID inptr,   
   LONG VfDelta,  
   PVOID SrcType,  
   PVOID TargetType,   
   BOOL isReference  
   ) throw(...)  
```  
  
#### Параметры  
 `inptr`  
 Указатель на полиморфный объект.  
  
 `VfDelta`  
 Смещение указателя на виртуальную функцию в объекте.  
  
 `SrcType`  
 Статический тип объекта, на который указывает параметр `inptr`.  
  
 `TargetType`  
 Планируемый результат преобразования.  
  
 `isReference`  
 `true` если аргумент — ссылка; `false` если аргумент — указатель.  
  
## Возвращаемое значение  
 Указатель на соответствующий под\-объект при успехе; в противном случае — NULL.  
  
## Исключения  
 `bad_cast()`, если входное значение `dynamic_cast<>` — ссылка и приведение завершается неудачей.  
  
## Заметки  
 Преобразует объект типа `inptr` в объект типа `TargetType`.  Тип `inptr` должен быть указателем, если `TargetType` — указатель, или L\-значением, если `TargetType` — ссылка.  `TargetType` должен быть указателям или ссылкой на ранее определенный тип класса или указателем на void.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|\_\_RTDynamicCast|rtti.h|