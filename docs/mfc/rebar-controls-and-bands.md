---
title: Элементы управления и зоны главной панели | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 988b16bb58462b42b8d4412a821cfc3fac5b4878
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443986"
---
# <a name="rebar-controls-and-bands"></a>Элементы управления и зоны главной панели

Основная цель элемент управления "Главная панель" — в качестве контейнера для дочерних окон, стандартные элементы управления диалогового окна, меню, панелей инструментов и т. д. Это вложение поддерживается концепция «полосы». Каждый аппаратного контроллера управления "Главная панель" может содержать любое сочетание полосу захвата, битовая карта, текстовую метку и дочернего окна.

Класс `CReBarCtrl` имеет многие функции-члены, можно использовать для получения и обрабатывать, эти данные для конкретных главной:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) возвращает номер текущего полосами в элементе управления "Главная панель".

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) инициализирует **REBARBANDINFO** структуру с данными из указанного диапазона. Есть соответствующая [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) функция-член.

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Извлекает ограничивающий прямоугольник указанный аппаратного контроллера управления.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) возвращает число строк аппаратного контроллера управления в элементе управления "Главная панель".

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) Извлекает индекс указанного диапазона.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) извлекает границы диапазона.

В дополнение к манипуляции предоставляются несколько функций-членов, которые позволяют работать с лентами определенной главной панели.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) и [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) добавлять и удалять лентами главной панели. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) и [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) влияют на текущий размер зону определенной главной панели. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) изменяет индекс определенной главной. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) показывает или скрывает от пользователя зону главной панели.

В следующем примере показано добавление панель инструментов (*m_wndToolBar*) для существующего элемента управления "Главная панель" (*m_wndReBar*). Диапазон описываемых инициализация `rbi` структуры и последующего вызова `InsertBand` функция-член:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>См. также

[Использование CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

