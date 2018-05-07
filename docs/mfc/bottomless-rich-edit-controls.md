---
title: Элементы управления Rich Edit "без дна" | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f2b08f6c04d345b4ae3ab32c6d0f17a1d8a4647
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bottomless-rich-edit-controls"></a>Элементы управления "Rich Edit" "без дна"
Приложение может изменить размер элемента управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) при необходимости, чтобы он всегда совпадает с размером его содержимого. Элемента управления rich edit поддерживает эти так называемые «без дна» функциональные возможности, отправляя родительского окна [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) уведомление при каждом изменении размера его содержимого.  
  
 При обработке **EN_REQUESTRESIZE** сообщение уведомления, приложения должны изменяться размеры элемента управления к измерениям в указанном [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) структуры. Приложение также может перемещать все сведения, рядом с элементом управления, чтобы вместить изменение высоты элемента управления. Чтобы изменить размер элемента управления, можно использовать `CWnd` функция [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).  
  
 Можно принудительно элемента управления "без дна rich edit" для отправки **EN_REQUESTRESIZE** сообщение уведомления с помощью [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) функции-члена. Это сообщение может быть полезен в [OnSize](../mfc/reference/cwnd-class.md#onsize) обработчика.  
  
 Для получения **EN_REQUESTRESIZE** сообщений уведомлений, необходимо включить уведомления с помощью `SetEventMask` функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

