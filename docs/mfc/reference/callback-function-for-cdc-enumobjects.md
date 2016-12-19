---
title: "Функция обратного вызова для CDC::EnumObjects | Microsoft Docs"
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
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции обратного вызова, для CDC::EnumObjects"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция обратного вызова для CDC::EnumObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Имя *ObjectFunc* заполнитель для приложения, переданного имени функции.  
  
## Синтаксис  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### Параметры  
 *lpszLogObject*  
 Указывает на структуре данных [LOGPEN](../../mfc/reference/logpen-structure.md) или [LOGBRUSH](../Topic/LOGBRUSH%20Structure.md), в которой содержатся сведения о логических атрибутов объекта.  
  
 `lpData`  
 Точки приложения к общим данным, переданной в `EnumObjects` функции.  
  
## Возвращаемое значение  
 Функция обратного вызова возвращает `int`.  Значение этого определяемо возвращают пользователем.  Если функция обратного вызова возвращает 0, `EnumObjects` останавливает перечисление ранее.  
  
## Заметки  
 Фактическое имя должны экспортироваться.  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)