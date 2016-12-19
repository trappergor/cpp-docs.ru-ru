---
title: "Функция обратного вызова для CDC::SetAbortProc | Microsoft Docs"
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
  - "Callback Function for CDC::SetAbortProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции обратного вызова, для CDC::SetAbortProc"
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция обратного вызова для CDC::SetAbortProc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Имя *AbortFunc* заполнитель для приложения, переданного имени функции.  
  
## Синтаксис  
  
```  
  
      BOOL CALLBACK EXPORT AbortFunc(   
   HDC hPr,   
   int code    
);  
```  
  
#### Параметры  
 *hPr*  
 Задает контекст устройства.  
  
 `code`  
 Определяет, произошла ли ошибка.  0, Если ошибка не происходила.  Значение **SP\_OUTOFDISK**, если диспетчер печати в данный момент нехватка места на диске и место на диске станет доступным, если приложение будет ожидать.  Если `code`**SP\_OUTOFDISK**, приложение не должно обрабатываться задание печати.  Если он не существует, он должен создать в диспетчер печати с помощью функции Windows **PeekMessage** или **GetMessage**.  
  
## Возвращаемое значение  
 Возвращаемое значение функции прекращени\- обработчика отлично от нуля, если задание печати продолжить, и 0, если оно отменено.  
  
## Заметки  
 Фактическое имя должны экспортироваться комментария, как описано в разделе [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md).  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)