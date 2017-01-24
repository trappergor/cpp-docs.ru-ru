---
title: "Структура PAINTSTRUCT | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PAINTSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PAINTSTRUCT - структура"
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура PAINTSTRUCT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `PAINTSTRUCT` содержит сведения, которые можно использовать для рисования клиентской области окна.  
  
## Синтаксис  
  
```  
  
      typedef struct tagPAINTSTRUCT {  
   HDC hdc;  
   BOOL fErase;  
   RECT rcPaint;  
   BOOL fRestore;  
   BOOL fIncUpdate;  
   BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### Параметры  
 *hdc*  
 Задает контекст отображения, который используется для заливки фона.  
  
 *fErase*  
 Указывает, необходимо ли фону быть перерисовке.  Он не равен 0, если приложение должно redraw фон.  Приложение отвечает за создание фон, если класс окна Windows создается без кисти фона, \(см. описание элемента **hbrBackground** структуры [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 *rcPaint*  
 Определяет верхней левой и правой стороны нижние углы прямоугольника, в котором производится рисование.  
  
 *fRestore*  
 Зарезервировано член.  Он используется внутренне Windows.  
  
 *fIncUpdate*  
 Зарезервировано член.  Он используется внутренне Windows.  
  
 *rgbReserved \[16\]*  
 Зарезервировано член.  Зарезервировано блок памяти, используемый внутри Windows.  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)