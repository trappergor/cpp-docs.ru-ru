---
title: Функции-члены счетчика
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 5ad6f529762e77e1cf1c00f41eea0add5d196fbb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307267"
---
# <a name="spin-button-member-functions"></a>Функции-члены счетчика

Существует несколько функций-членов, доступных для управления "Счетчик" ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Используйте эти функции, чтобы изменить следующие атрибуты элемента кнопка "Счетчик".

- **Ускорение** можно настроить частоту, с которой положение изменений, когда пользователь удерживает кнопку со стрелкой. Для работы с ускорением используйте [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) и [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) функций-членов.

- **Базовый** базы (10 или 16), используемый для отображения позиции в заголовке в связанном окне можно изменить. Для работы с базой, используйте [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) и [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) функций-членов.

- **Приятель окно** вы можете динамически устанавливать в связанном окне. Чтобы запросить или изменить, какой элемент управления является окном buddy, используйте [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) и [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) функций-членов.

- **Позиция** можно запросить или изменить положение. Для работы непосредственно с позиции, используйте [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) и [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) функций-членов. Так как подпись элемента управления buddy могло измениться (например, в случае что контактов является элементом управления), `GetPos` извлекает текущий заголовок и корректирует положение соответствующим образом.

- **Диапазон** можно изменить максимальное и минимальное позиции для кнопка "Счетчик". По умолчанию максимальное имеет значение 0, и минимальное значение — 100. Так как по умолчанию максимальное значение меньше, чем минимальное значение по умолчанию, нелогичными действия кнопки со стрелками. Как правило, устанавливается диапазон с помощью [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) функция-член. Чтобы запросить использование диапазона [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).

## <a name="see-also"></a>См. также

[Использование CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
