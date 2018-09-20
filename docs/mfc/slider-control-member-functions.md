---
title: Функции-члены элемента управления "ползунок" | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f3c7c9d2b1cfd863f2c76a6f0ce9de197912786
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377517"
---
# <a name="slider-control-member-functions"></a>Функции-члены элемента управления "Ползунок"

Приложение может вызвать ползунок функции-члены элемента управления для получения сведений об элементе управления "ползунок" ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) и изменить его характеристики.

Для получения позиции ползунка (то есть значение, пользователь выбрал), используйте [GetPos](../mfc/reference/csliderctrl-class.md#getpos) функция-член. Чтобы задать положение ползунка, используйте [SetPos](../mfc/reference/csliderctrl-class.md#setpos) функция-член. В любое время можно использовать `VerifyPos` функцию-член для убедитесь, что ползунок находится между минимальным и максимальным значениями.

Диапазон элемента управления "ползунок" — это набор непрерывных значений, которые могут представлять элемент управления "ползунок". Большинство приложений используют [SetRange](../mfc/reference/csliderctrl-class.md#setrange) функция-член Чтобы задать диапазон элемента управления "ползунок", при ее создании. После создания элемента управления slider с помощью приложения динамически можно изменить диапазон [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) и [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) функций-членов. Приложение, в которой можно изменять динамически обычно извлекает параметры окончательного диапазона, когда пользователь закончил работу с элементом управления "ползунок". Чтобы получить эти параметры, используйте [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), и [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) функций-членов.

Приложение может использовать TBS_AUTOTICKS стиль для элемента управления "ползунок" делений, отображаемых автоматически. Если приложению для управления положения или частоту делений, тем не менее, можно использовать ряд функций-членов.

Чтобы установить позицию делений, приложение может использовать [SetTic](../mfc/reference/csliderctrl-class.md#settic) функция-член. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) функция-член позволяет приложению задать деления, метки, которые отображаются с регулярными интервалами, в диапазоне элемента управления "ползунок". Например приложение может использовать эту функцию-член для отображения только 10 деления в диапазоне от 1 до 100.

Для получения индекса в диапазон, соответствующий деления, используйте [GetTic](../mfc/reference/csliderctrl-class.md#gettic) функция-член. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) функция-член возвращает массив этих индексов. Чтобы получить позицию делений, в координатах клиентской области окна, используйте [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) функция-член. Приложение может получить количество делений, с помощью [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) функция-член.

[ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) функция-член удаляет все делений для элемента управления "ползунок".

Размер строки элемента управления "ползунок" определяет, насколько далеко перемещается ползунок, когда приложение получает сообщение уведомления TB_LINEDOWN или TB_LINEUP. Аналогичным образом размер страницы определяет ответ TB_PAGEDOWN и TB_PAGEUP сообщений уведомления. Приложения можно получать и задавать значения размера строки и страницы с помощью [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), и [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) функций-членов.

Приложение может использовать функции-члены для извлечения элемента управления "ползунок". [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) функция-член извлекает ограничивающий прямоугольник для ползунка. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) функция-член Возвращает ограничивающий прямоугольник, канал управления "ползунок". (Канал — это область над ползунок также увеличивает и при выборе диапазона, который содержит выделение).

Если элемент управления "ползунок" стиль TBS_ENABLESELRANGE, пользователь может выбрать диапазон смежных значений из него. Ряд функций-членов разрешить диапазон выбора корректироваться динамически. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) функция-член задает начальное и конечное положение выделения. По завершении установки диапазон выбора пользователя приложение может извлечь параметры с помощью [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) функция-член. Чтобы очистить Выбор пользователя, используйте [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) функция-член.

## <a name="see-also"></a>См. также

[Использование CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

