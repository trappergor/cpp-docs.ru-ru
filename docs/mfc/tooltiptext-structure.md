---
title: Структура TOOLTIPTEXT | Документация Майкрософт
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
ms.openlocfilehash: 0f65b94294b3b3d55f9839dffa99a18be61c5639
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195988"
---
# <a name="tooltiptext-structure"></a>Структура TOOLTIPTEXT
В письменной вашей [обработчик уведомлений подсказки](../mfc/handling-ttn-needtext-notification-for-tool-tips.md), необходимо использовать **TOOLTIPTEXT** структуры. Члены **TOOLTIPTEXT** структуры являются:  
  
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
 Идентифицирует средство, которое требуется текст. Единственный член этой структуры, которые могут потребовать является идентификатор команды элемента управления. Идентификатор команды элемента управления будет находиться в *idFrom* членом **NMHDR** структуры, получить доступ с помощью синтаксиса `hdr.idFrom`. См. в разделе [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) обсуждение членами **NMHDR** структуры.  
  
 *lpszText*  
 Адрес строки для получения текста для средства.  
  
 *szText*  
 Буфер, получающий текст подсказки. Приложения можно скопировать текст в этот буфер в качестве альтернативы для указания строки адреса.  
  
 *hinst*  
 Дескриптор экземпляра, который содержит строку для использования в качестве текст подсказки. Если *lpszText* — это адрес текста подсказки, этот элемент имеет значение NULL.  
  
 При обработке `TTN_NEEDTEXT` уведомления сообщений, укажите строку для отображения в одном из следующих способов:  
  
-   Скопируйте текст в буфер, определяемое *szText* член.  
  
-   Скопируйте адрес буфера, который содержит текст, *lpszText* член.  
  
-   Скопируйте идентификатор строкового ресурса для *lpszText* член и копирования дескриптор экземпляра, содержащего ресурс *hinst* член.  
  
## <a name="see-also"></a>См. также  
 [Подсказки в Windows, не являющиеся производными от CFrameWnd](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

