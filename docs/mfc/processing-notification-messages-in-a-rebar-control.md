---
title: Обработка уведомляющих сообщений в элементах управления главной панели | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a1d42d129ab7b7d2e98ae1126b8f32f68b1f356
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931831"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Обработка уведомляющих сообщений в элементах управления главной панели
В родительском классе элемента управления главной панели, создайте `OnChildNotify` функция обработчика с инструкцию switch для любой управления главной панели (`CReBarCtrl`) для обработки сообщений уведомления. Уведомления отправляются родительского окна при перетаскивании объектов на элемент управления главной панели, изменения макета лентами главной панели, а операции удаления зоны из контейнера элементов управления и т. д.  
  
 Следующие сообщения уведомления могут отправляться объект элемента управления главной панели:  
  
-   Посылается элементом управления главной панели (созданная с параметром стиля RBS_AUTOSIZE), RBN_AUTOSIZE при главной панели автоматически изменять свои размеры.  
  
-   RBN_BEGINDRAG посылается элементом управления главной панели, когда пользователь начинает перетаскивать полосе.  
  
-   RBN_CHILDSIZE посылается элементом управления главной панели при изменении размера дочернее окно полосы.  
  
-   RBN_DELETEDBAND посылается элементом управления главной панели после удаления полосе.  
  
-   RBN_DELETINGBAND посылается элементом управления главной панели при полосе которой нужно удалить.  
  
-   RBN_ENDDRAG посылается элементом управления главной панели, когда пользователь отпускает полосе.  
  
-   Посылается элементом управления главной панели (созданная с параметром стиля RBS_REGISTERDROP), RBN_GETOBJECT когда объект перетаскивается на полосе в элементе управления.  
  
-   RBN_HEIGHTCHANGE посылается элементом управления главной панели при изменении его высота.  
  
-   RBN_LAYOUTCHANGED посылается элементом управления главной панели при изменении вида элемента управления зоны.  
  
 Дополнительные сведения об этих уведомлений см. в разделе [ссылки на элемент управления главной панели](http://msdn.microsoft.com/library/windows/desktop/bb774375) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

