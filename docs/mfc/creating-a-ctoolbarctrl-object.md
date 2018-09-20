---
title: Создание объекта CToolBarCtrl | Документация Майкрософт
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
ms.openlocfilehash: c98f99ef7ff26fed7d7df89881d2148af6bc993a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421652"
---
# <a name="creating-a-ctoolbarctrl-object"></a>создание объекта CToolBarCtrl

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекты содержат несколько внутренних структур данных — список точечного рисунка изображения для кнопки, список строк метки кнопки и список `TBBUTTON` структуры —, связать изображение и/или строка с позиции, стиль, состояние, и Идентификатор команды кнопки. Каждый из элементов этих структур данных ссылается отсчитываемый от нуля индекс. Перед использованием `CToolBarCtrl` объекта, необходимо настроить эти структуры данных. Список структур данных, см. в разделе [элементы управления панели инструментов](controls-mfc.md) в пакете Windows SDK. Список строк может использоваться только для надписей на кнопках; не удается извлечь строки из панели инструментов.

Чтобы использовать `CToolBarCtrl` объекта, вы обычно выполняются следующие действия:

### <a name="to-use-a-ctoolbarctrl-object"></a>Для использования объекта CToolBarCtrl

1. Создать [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) объекта.

1. Вызовите [создать](../mfc/reference/ctoolbarctrl-class.md#create) для создания общего элемента управления панели инструментов Windows и присоединить его к `CToolBarCtrl` объекта. Растровые изображения для кнопок, добавить точечного рисунка для кнопки на панели инструментов, вызвав [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Если требуется строка подписи для кнопок, добавлять строки панели инструментов, вызвав [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) и/или [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). После вызова метода `AddString` и/или `AddStrings`, следует вызывать [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) для получения в строку или строки будут выводиться.

1. Добавьте структур кнопки панели инструментов, вызвав метод [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).

1. Всплывающие подсказки следует обрабатывать **TTN_NEEDTEXT** сообщений в окно-владелец панели инструментов, как описано в разделе [обработка уведомлений всплывающих совет](../mfc/handling-tool-tip-notifications.md).

1. Если требуется, чтобы пользователь имел возможность настроить панель инструментов, обрабатывать настройки уведомляющих сообщений в окно-владелец, как описано в разделе [обработка уведомлений о настройке](../mfc/handling-customization-notifications.md).

## <a name="see-also"></a>См. также

[Использование CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

