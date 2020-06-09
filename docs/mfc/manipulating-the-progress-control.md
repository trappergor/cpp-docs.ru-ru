---
title: Управление элементом управления "Индикатор выполнения"
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
ms.openlocfilehash: 3e3521a82854a85062f9b06bc33eb268d4b9c7a6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622435"
---
# <a name="manipulating-the-progress-control"></a>Управление элементом управления "Индикатор выполнения"

Существует три способа изменить текущее расположение элемента управления ходом выполнения ([CProgressCtrl](reference/cprogressctrl-class.md)).

- Эту точку можно изменить с помощью предустановленной суммы приращения.

- Эту точку можно изменить произвольным объемом.

- Расположение можно изменить на определенное значение.

### <a name="to-change-the-position-by-a-preset-amount"></a>Изменение расположения на заданную сумму

1. Используйте функцию члена [сетстеп](reference/cprogressctrl-class.md#setstep) , чтобы задать величину приращения. По умолчанию это значение равно 10. Это значение обычно задается в качестве одного из начальных параметров для элемента управления. Значение шага может быть отрицательным.

1. Чтобы увеличить эту точку, используйте функцию члена [степит](reference/cprogressctrl-class.md#stepit) . В результате элемент управления перерисовывается самим собой.

    > [!NOTE]
    >  `StepIt`приведет к переносу расположения. Например, если задать диапазон 1 -100, шаг 20 и расположение 90, `StepIt` будет установлено значение 10.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Изменение расположения на произвольный объем

1. Для изменения расположения используйте функцию члена [оффсетпос](reference/cprogressctrl-class.md#offsetpos) . `OffsetPos`принимает отрицательные значения.

    > [!NOTE]
    >  `OffsetPos`, в отличие от `StepIt` , не будет переносить эту точку в оболочку. Новое расположение корректируется, чтобы остаться в пределах диапазона.

### <a name="to-change-the-position-to-a-specific-value"></a>Изменение расположения на определенное значение

1. Используйте функцию-член [сетпос](reference/cprogressctrl-class.md#setpos) , чтобы задать в качестве расположения определенное значение. При необходимости новое расположение корректируется в пределах диапазона.

Как правило, элемент управления progress используется исключительно для вывода. Чтобы получить текущую точку без указания нового значения, используйте [жетпос](reference/cprogressctrl-class.md#getpos).

## <a name="see-also"></a>См. также раздел

[Использование CProgressCtrl](using-cprogressctrl.md)<br/>
[Элементы управления](controls-mfc.md)
