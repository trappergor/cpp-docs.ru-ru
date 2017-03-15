---
title: "MSG Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSG - структура"
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура MSG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `MSG` содержит данные сообщения из очереди сообщений потока.  
  
## Синтаксис  
  
```  
  
      typedef struct tagMSG {     // msg    
   HWND hwnd;  
   UINT message;  
   WPARAM wParam;  
   LPARAM lParam;  
   DWORD time;  
   POINT pt;  
} MSG;  
```  
  
#### Параметры  
 *hwnd*  
 Определяет окно процедура окна, получает сообщение.  
  
 `message`  
 Задает номер сообщения.  
  
 `wParam`  
 Задает дополнительные сведения о сообщении.  Точное значение зависит от значения элемента **message**.  
  
 `lParam`  
 Задает дополнительные сведения о сообщении.  Точное значение зависит от значения элемента **message**.  
  
 `time`  
 Определяет время, в которой сообщение отправлено.  
  
 `pt`  
 Задает положение курсора в экранных координатах, когда сообщение отправлено.  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)