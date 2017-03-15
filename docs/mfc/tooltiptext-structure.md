---
title: "Структура TOOLTIPTEXT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TOOLTIPTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "всплывающие подсказки [C++], уведомления"
  - "TOOLTIPTEXT - структура"
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Структура TOOLTIPTEXT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В записи в [обработчик уведомления всплывающей подсказки](../Topic/Handling%20TTN_NEEDTEXT%20Notification%20for%20Tool%20Tips.md), необходимо использовать структуру `TOOLTIPTEXT`.  Члены структуры `TOOLTIPTEXT`:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 Определяет средство, которое требуется текст.  Единственный член этой структуры можно идентификатор команды элемента управления  Идентификатор команды элемента управления находится в элементе `idFrom` структуры `NMHDR`, получил доступ с синтаксисом `hdr.idFrom`.  В разделе [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) для обсуждения членов структуры `NMHDR`.  
  
 `lpszText`  
 Адрес строки для получения текста для средства.  
  
 `szText`  
 Буфер, который получает текст всплывающей подсказки.  Приложение может копировать текст в этот буфер в качестве альтернативы определение адрес строки.  
  
 `hinst`  
 Дескриптор экземпляра, который содержит строку, используемый в качестве текст всплывающей подсказки.  Если `lpszText` адрес текст всплывающей подсказки, то этот член NULL.  
  
 При обработке сообщения уведомления `TTN_NEEDTEXT` укажите строку для отображения одним из следующих способов:  
  
-   Скопируйте текст в буфер, членом `szText`.  
  
-   Скопируйте адрес буфера, содержащего текст на член `lpszText`.  
  
-   Скопируйте идентификатор строки ресурсов на член `lpszText` и скопировать дескриптор экземпляра, содержащему ресурс на член `hinst`.  
  
## См. также  
 [Всплывающие подсказки в Windows, не являющиеся производными CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)