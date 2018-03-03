---
title: "Создание заголовка элемента управления | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33f536a86a21e56eb36e546109f916ae5d6ca806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-header-control"></a>Создание элемента управления "Заголовок"
Элемент управления заголовка недоступен непосредственно в редакторе диалоговых окон (несмотря на то, что можно добавить элемент управления "список", который включает элемент управления заголовка).  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>Перевод заголовка элемента управления в диалоговое окно  
  
1.  Вручную внедрить переменную-член типа [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) в класс диалогового окна.  
  
2.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), создание и установка стилей для `CHeaderCtrl`, расположите его и откройте его.  
  
3.  Добавьте элементы управления заголовка.  
  
4.  Используйте в окне «Свойства» для сопоставления функции обработчика в класс диалоговых окон для всех уведомлений, управления заголовка сообщения, вы должны обрабатывать (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Чтобы разместить элемент управления заголовка в представлении (не CListView)  
  
1.  Внедрение [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) объекта в классе представления.  
  
2.  Стиль, размещение и окно управления заголовка в представлении [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функции-члена.  
  
3.  Добавьте элементы управления заголовка.  
  
4.  Используйте в окне «Свойства» для сопоставления обработчика функций в классе представления для всех уведомлений, управления заголовка сообщения, вы должны обрабатывать (см. [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
 В любом случае объект внедренный элемент управления создается при создании объекта представления или диалогового окна. Следует вызвать [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) для создания окна элемента управления. Чтобы разместить элемент управления, вызовите [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) определить исходный размер и положение элемента управления и [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) задаваемое в нужное место. Затем добавьте элементы, как описано в [Добавление элементов управления заголовка](../mfc/adding-items-to-the-header-control.md).  
  
 Дополнительные сведения см. в разделе [Создание элемента управления заголовка](http://msdn.microsoft.com/library/windows/desktop/bb775238) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

