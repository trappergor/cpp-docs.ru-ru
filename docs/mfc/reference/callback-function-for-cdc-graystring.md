---
title: "Функция обратного вызова для CDC::GrayString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::GrayString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции обратного вызова, для CDC::GrayString"
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Функция обратного вызова для CDC::GrayString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*OutputFunc* заполнитель для приложения, переданного имени функции обратного вызова.  
  
## Синтаксис  
  
```  
  
      BOOL CALLBACK EXPORT OutputFunc(   
   HDC hDC,   
   LPARAM lpData,   
   int nCount    
);  
```  
  
#### Параметры  
 `hDC`  
 Задает контекст устройством хранения с растровым изображением по крайней мере ширины и высоты, `nWidth` и `nHeight` в `GrayString`.  
  
 `lpData`  
 Указывает на символьной строки, который необходимо создать.  
  
 `nCount`  
 Указывает число символов для вывода.  
  
## Возвращаемое значение  
 Возвращаемое значение функции обратного вызова должно быть **TRUE** отображаются успешное завершение; в противном случае — значение **ЛОЖЬ**.  
  
## Заметки  
 Функция обратного вызова \(*OutputFunc*\) должна создать образ относительно координаты \(0,0\), а не \(*x*, *y*\).  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../Topic/CDC::GrayString.md)