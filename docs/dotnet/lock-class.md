---
title: "Класс lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock"
  - "msclr.lock"
  - "lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock - класс"
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс выполняет блокировку для автоматизации синхронизировать доступ к объекту из нескольких потоков.  Построенный ему получает блокировку и разрушанный его выпуски блокировку.  
  
## Синтаксис  
  
```  
ref class lock;  
```  
  
## Заметки  
 `lock` доступно только для объектов среды CLR и может использоваться только в коде среды CLR.  
  
 По сути, класс блокировки используется <xref:System.Threading.Monitor> синхронизировать доступ.  См. в статье более подробные сведения о синхронизации.  
  
## Требования  
 **Файл заголовка**\<msclr\\lock.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [lock](../dotnet/lock.md)   
 [Блокировка членов](../dotnet/lock-members.md)