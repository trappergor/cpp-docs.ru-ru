---
title: "Конструктор CriticalSection::CriticalSection | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection, конструктор"
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Конструктор CriticalSection::CriticalSection
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует объект синхронизации, аналогичный объекту мьютекса, который может использоваться только потоками одного процесса.  
  
## Синтаксис  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### Параметры  
 `spincount`  
 Счетчик прокруток для объекта критической секции.  Значение по умолчанию — 0.  
  
## Примечания  
 Для получения дополнительных сведений о критических секциях см. функцию **InitializeCriticalSectionAndSpinCount** в разделе Синхронизации документации Windows API.  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Класс CriticalSection](../Topic/CriticalSection%20Class.md)