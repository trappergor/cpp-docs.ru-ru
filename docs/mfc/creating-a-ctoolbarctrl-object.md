---
title: Создание объекта CToolBarCtrl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c5e2ee8c0e2239de86252b3d0fb8ec0ab7cc182
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-ctoolbarctrl-object"></a>создание объекта CToolBarCtrl
[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекты содержат несколько внутренних структур данных — список точечного рисунка для изображения кнопки, список строк метки кнопки и список `TBBUTTON` структуры —, связать изображение и/или строка с позиции, стиль, состояние, и Идентификатор команды кнопки. Каждый из элементов этих структур данных ссылается отсчитываемый от нуля индекс. Прежде чем использовать `CToolBarCtrl` объекта, необходимо настроить эти структуры данных. Список структур данных см. в разделе [элементы управления панели инструментов](controls-mfc.md) в Windows SDK. Список строк может использоваться только для метки кнопок; не удается получить строки на панели инструментов.  
  
 Для использования `CToolBarCtrl` объекта, обычно выполняются следующие действия:  
  
### <a name="to-use-a-ctoolbarctrl-object"></a>Для использования объекта CToolBarCtrl  
  
1.  Создать [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта.  
  
2.  Вызовите [создать](../mfc/reference/ctoolbarctrl-class.md#create) для создания стандартного элемента управления панель инструментов Windows и присоединить его к `CToolBarCtrl` объекта. Растровые изображения для кнопок, добавить точечного рисунка для кнопки панели инструментов, вызвав [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Если требуется строка подписи для кнопок, добавлять строки панели инструментов, вызвав [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) и/или [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). После вызова метода `AddString` и/или `AddStrings`, необходимо вызвать [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) для получения строки или строки будут выводиться.  
  
3.  Добавить структуры кнопки панели инструментов с помощью [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).  
  
4.  Всплывающие подсказки, обработать **TTN_NEEDTEXT** сообщений в панели инструментов окна-владельца, как описано в [обработка уведомлений всплывающих совет](../mfc/handling-tool-tip-notifications.md).  
  
5.  Если вы хотите ваши пользователи, чтобы иметь возможность настроить панель инструментов, обрабатывать настройки уведомляющих сообщений в окно-владелец, как описано в [обработка уведомлений о настройке](../mfc/handling-customization-notifications.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

