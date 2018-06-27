---
title: Структура TOOLTIPTEXT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8cae7efbee59b24ff34518b62ff212d436973053
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953936"
---
# <a name="tooltiptext-structure"></a>Структура TOOLTIPTEXT
При записи вашего [обработчик уведомлений совет средство](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), необходимо использовать **TOOLTIPTEXT** структуры. Члены **TOOLTIPTEXT** структуры являются:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 *HDR*  
 Идентифицирует средство, которое требуется текст. Единственным членом этой структуры, которые могут потребовать является идентификатор команды элемента управления. Идентификатор команды элемента управления будет находиться в *idFrom* членом **NMHDR** структуру, доступ с помощью синтаксиса `hdr.idFrom`. В разделе [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) обсуждение члены **NMHDR** структуры.  
  
 *lpszText*  
 Адрес строки для получения текста для средства.  
  
 *szText*  
 Буфер, который получает текст подсказки. Приложения можно скопировать текст в буфер вместо указания адреса строки.  
  
 *hinst*  
 Дескриптор экземпляра, который содержит строку для использования в качестве текст подсказки. Если *lpszText* адрес текст подсказки, этот член является NULL.  
  
 При обработке `TTN_NEEDTEXT` уведомления сообщений, укажите строку, отображаемую в один из следующих способов:  
  
-   Скопируйте текст в буфер, определяемое *szText* член.  
  
-   Адрес буфера, который содержит текст, скопируйте *lpszText* член.  
  
-   Скопируйте идентификатор строкового ресурса для *lpszText* член и копирования дескриптор экземпляра, содержащего ресурс *hinst* член.  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

