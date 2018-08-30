---
title: Создание элемента управления заголовка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18517f969dc64b0c1d9a51bcdc67a1655ec82d7c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214013"
---
# <a name="creating-the-header-control"></a>Создание элемента управления "Заголовок"
Элемент управления заголовка не доступны напрямую в редакторе диалоговых окон (хотя можно добавить элемент управления "список", который включает элемент управления заголовка).  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>Чтобы поместить элемент управления заголовка в диалоговом окне  
  
1.  Вручную внедрить переменную-член типа [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) в классов диалоговых окон.  
  
2.  В [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), создание и установка стилей для `CHeaderCtrl`, поместите ее и отобразить ее.  
  
3.  Добавьте элементы управления заголовка.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в класс диалоговых окон для всех уведомлений, управления заголовка сообщения, вы должны обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Чтобы поместить элемент управления заголовка в представлении (не CListView)  
  
1.  Внедрение [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) объекта в классе представления.  
  
2.  Стиль, размещение и отображение окна элемента управления заголовка в представлении [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) функция-член.  
  
3.  Добавьте элементы управления заголовка.  
  
4.  Используйте окно свойств для сопоставления функции обработчика в классе представления для всех уведомлений, управления заголовка сообщения, вы должны обрабатывать (см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md)).  
  
 В любом случае объект внедренный элемент управления создается при создании объекта представления или диалогового окна. Затем необходимо вызвать [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) для создания окна элемента управления. Чтобы разместить элемент управления, вызовите [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) для определения исходный размер и положение элемента управления и [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) задать нужное место. Затем добавьте элементы, как описано в разделе [Добавление элементов управления заголовка](../mfc/adding-items-to-the-header-control.md).  
  
 Дополнительные сведения см. в разделе [Создание элемента управления заголовка](/windows/desktop/Controls/header-controls) в пакете Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

