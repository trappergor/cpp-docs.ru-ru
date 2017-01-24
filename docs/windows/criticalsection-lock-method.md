---
title: "Метод CriticalSection::Lock | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock - метод"
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод CriticalSection::Lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ожидание владения объектом указанной критической секции.  Функция возвращает, когда вызывающему потоку предоставляются права владельца.  
  
## Синтаксис  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Параметры  
 `cs`  
 Определенный пользователем объект критической секции.  
  
## Возвращаемое значение  
 Объект блокировки, который можно использовать, чтобы разблокировать текущую критическую секцию.  
  
## Примечания  
 Первая функция **Lock** влияет на текущий объект критической секции.  Вторая функция **Lock** влияет на указанную пользователем критическую секцию.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс CriticalSection](../Topic/CriticalSection%20Class.md)