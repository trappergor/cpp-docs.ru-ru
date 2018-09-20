---
title: Добавление элементов управления в лист свойств | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0783571ed77d3d8dfaca69edf06330e62d8e98d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398512"
---
# <a name="adding-controls-to-a-property-sheet"></a>Добавление элементов управления на вкладку свойств

По умолчанию страницу свойств выделяет область окна для страницы свойств, индекс вкладки и кнопки ОК, Отмена и применить. (Немодальный лист свойств не поддерживает ОК, Отмена и применить кнопки.) Можно добавить другие элементы управления в лист свойств. Например можно добавить в окно предварительного просмотра справа от области страницы свойств, чтобы показать пользователю, как будет выглядеть текущие параметры, если применяется к внешнему объекту.

Можно добавить элементы управления в диалоговом окне страницы свойств в `OnCreate` обработчика. Размещении дополнительные элементы управления обычно требуется увеличение размера диалоговое окно страницы свойств. После вызова базового класса **CPropertySheet::OnCreate**, вызовите [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) для получения, ширину и высоту окна листа свойств, выделенных на данный момент, разверните прямоугольника измерения и вызова [Функции MoveWindow](../mfc/reference/cwnd-class.md#movewindow) для изменения размера окна листа свойств.

## <a name="see-also"></a>См. также

[Страницы свойств](../mfc/property-sheets-mfc.md)<br/>
[Класс CPropertyPage](../mfc/reference/cpropertypage-class.md)<br/>
[Класс CPropertySheet](../mfc/reference/cpropertysheet-class.md)
