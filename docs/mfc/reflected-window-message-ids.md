---
title: Отображаются идентификаторы сообщений окон | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OCM_CTLCOLORBTN
- OCM_PARENTNOTIFY
- OCM_VKEYTOITEM
- OCM_CTLCOLORSTATIC
- OCM_HSCROLL
- OCM_CHARTOITEM
- OCM_DRAWITEM
- OCM_MEASUREITEM
- OCM_COMPAREITEM
- OCM_COMMAND
- OCM_NOTIFY
- OCM_CTLCOLORMSGBOX
- OCM_DELETEITEM
- OCM_CTLCOLORLISTBOX
- OCM_CTLCOLORDLG
- OCM_CTLCOLOREDIT
- OCM_CTLCOLORSCROLLBAR
- OCM_VSCROLL
- OCM_CTLCOLOR
dev_langs:
- C++
helpviewer_keywords:
- OCM_HSCROLL message [MFC]
- OCM_PARENTNOTIFY message [MFC]
- messages, reflected
- reflected messages, window message Ids
- OCM_CTLCOLORDLG message [MFC]
- OCM_COMMAND message [MFC]
- OCM_CTLCOLORMSGBOX message [MFC]
- OCM_COMPAREITEM message [MFC]
- OCM_DRAWITEM message [MFC]
- OCM_VSCROLL message [MFC]
- OCM_CTLCOLOREDIT message [MFC]
- OCM_VKEYTOITEM message [MFC]
- OCM_CHARTOITEM message [MFC]
- OCM_CTLCOLORBTN message [MFC]
- OCM_CTLCOLORSTATIC message [MFC]
- OCM_MEASUREITEM message [MFC]
- OCM_CTLCOLOR message [MFC]
- OCM_CTLCOLORSCROLLBAR message [MFC]
- OCM_ messages
- OCM_DELETEITEM message [MFC]
- OCM_CTLCOLORLISTBOX message [MFC]
- OCM_NOTIFY message [MFC]
- reflected messages
ms.assetid: 3417ff51-ff9f-458c-bff4-17c200f00d96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8746666c4b1eb48e4c54822f76328579b7ce8584
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928202"
---
# <a name="reflected-window-message-ids"></a>Отраженные идентификаторы сообщений окон
Подкласс быстрый способ создания элемента управления ActiveX или другие специальные управляющие — это окно. Дополнительные сведения см. в разделе [элементы управления MFC ActiveX: Создание подкласса элемента управления Windows Forms](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 Чтобы предотвратить получение сообщений окна, отправленных в элемент управления Windows, контейнер элемента управления [COleControl](../mfc/reference/colecontrol-class.md) создает окно «reflector» для перехвата определенных сообщений окна и отправить их обратно в элемент управления. Элемент управления в его процедуру окна, затем могут обработать эти отраженные сообщения, выполнив действия, которые соответствуют для элемента управления ActiveX.  
  
 Ниже приведены сообщения, которые могут быть перехвачены и соответствующие сообщения, отправляемые в окне «reflector».  
  
|Сообщение, отправленное с помощью элемента управления|Сообщение, отражаются в элемент управления|  
|---------------------------------|--------------------------------------|  
|[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)|OCM_COMMAND|  
|[WM_CTLCOLORBTN](http://msdn.microsoft.com/library/windows/desktop/bb761849)|OCM_CTLCOLORBTN|  
|[WM_CTLCOLOREDIT, КОТОРЫЕ](http://msdn.microsoft.com/library/windows/desktop/bb761691)|OCM_CTLCOLOREDIT|  
|[WM_CTLCOLORDLG](http://msdn.microsoft.com/library/windows/desktop/ms645417)|OCM_CTLCOLORDLG|  
|[WM_CTLCOLORLISTBOX](http://msdn.microsoft.com/library/windows/desktop/bb761360)|OCM_CTLCOLORLISTBOX|  
|[WM_CTLCOLORSCROLLBAR](http://msdn.microsoft.com/library/windows/desktop/bb787573)|OCM_CTLCOLORSCROLLBAR|  
|[WM_CTLCOLORSTATIC](http://msdn.microsoft.com/library/windows/desktop/bb787524)|OCM_CTLCOLORSTATIC|  
|[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)|OCM_DRAWITEM|  
|[WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925)|OCM_MEASUREITEM|  
|[WM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb761362)|OCM_DELETEITEM|  
|[WM_VKEYTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761364)|OCM_VKEYTOITEM|  
|[WM_CHARTOITEM](http://msdn.microsoft.com/library/windows/desktop/bb761358)|OCM_CHARTOITEM|  
|[WM_COMPAREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775921)|OCM_COMPAREITEM|  
|[WM_HSCROLL](http://msdn.microsoft.com/library/windows/desktop/bb787575)|OCM_HSCROLL|  
|[WM_VSCROLL](http://msdn.microsoft.com/library/windows/desktop/bb787577)|OCM_VSCROLL|  
|[WM_PARENTNOTIFY](https://msdn.microsoft.com/library/ms632638.aspx)|OCM_PARENTNOTIFY|  
|[WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)|OCM_NOTIFY|  
  
> [!NOTE]
>  Если элемент управления выполняется в системе Win32, существует несколько типов WM_CTLCOLOR\* она может получать сообщения. Дополнительные сведения см. в разделе WM_CTLCOLORBTN, WM_CTLCOLORDLG, WM_CTLCOLOREDIT, которые, WM_CTLCOLORLISTBOX, WM_CTLCOLORMSGBOX, WM_CTLCOLORSCROLLBAR, WM_CTLCOLORSTATIC.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC: Создание подкласса элемента управления Windows Forms](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)   
 [TN062. Отражение сообщений для элементов управления окнами](../mfc/tn062-message-reflection-for-windows-controls.md)

