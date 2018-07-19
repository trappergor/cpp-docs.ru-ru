---
title: Функции-члены элемента управления "ползунок" | Документы Microsoft
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
ms.openlocfilehash: 14e6df9a5d4dc6631b6891f90b55b63b73989b30
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953962"
---
# <a name="slider-control-member-functions"></a>Функции-члены элемента управления "Ползунок"
Приложение может вызвать ползунок функции-члены элемента управления для получения сведений об элементе управления "ползунок" ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) и изменить его характеристики.  
  
 Для получения позиции ползунка (то есть, значения, пользователь выберет), используйте [GetPos](../mfc/reference/csliderctrl-class.md#getpos) функции-члена. Чтобы задать положение ползунка, используйте [SetPos](../mfc/reference/csliderctrl-class.md#setpos) функции-члена. В любое время можно использовать `VerifyPos` функции-члена для убедитесь, что ползунок находится между минимальным и максимальным значениями.  
  
 Список элементов управления "ползунок" представляет собой последовательные значения, которые могут представлять элемент управления "ползунок". Большинство приложений используют [SetRange](../mfc/reference/csliderctrl-class.md#setrange) функцию-член, чтобы задать диапазон элемента управления "ползунок", при ее создании. После создания управления "ползунок" с помощью приложения динамически можно изменить диапазон [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) и [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) функции-члены. Приложение, позволяющее диапазон должен быть изменен динамически обычно получает параметры конечного диапазона, когда пользователь закончил работу с элементом управления "ползунок". Чтобы получить эти сведения, используйте [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), и [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) функции-члены.  
  
 Приложение может использовать стиль TBS_AUTOTICKS иметь элемент управления "ползунок" делений, отображаемых автоматически. Если приложению для управления положение или частоту делений, тем не менее, можно использовать ряд функций-членов.  
  
 Чтобы установить позицию делений, приложение может использовать [SetTic](../mfc/reference/csliderctrl-class.md#settic) функции-члена. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) функция-член позволяет приложению задать деления, метки, отображаемых через регулярные интервалы в диапазоне управления "ползунок". Например приложение может использовать эту функцию-член для отображения только 10 деления в диапазоне от 1 до 100.  
  
 Для получения индекса в диапазон, соответствующий деления используйте [GetTic](../mfc/reference/csliderctrl-class.md#gettic) функции-члена. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) функция-член возвращает массив этих индексов. Для получения позиции делений, в клиентских координатах, используйте [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) функции-члена. Приложение может получить количество делений, с помощью [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) функции-члена.  
  
 [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) функция-член удаляет все делений для элемента управления "ползунок".  
  
 Размер строки элемента управления "ползунок" определяет, насколько далеко перемещается ползунок, когда приложение получает сообщение уведомления TB_LINEDOWN или TB_LINEUP. Аналогично размер страницы определяет ответ на TB_PAGEDOWN и TB_PAGEUP сообщений уведомления. Приложения можно получать и задавать значения размера страниц и с помощью [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), и [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) функции-члены.  
  
 Приложение может использовать функции-члены для извлечения элемента управления "ползунок". [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) функция-член возвращает прямоугольник, ограничивающий для ползунка. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) функция-член возвращает прямоугольник, ограничивающий для канала управления "ползунок". (Канал является областью, на которое перемещается ползунок и при выборе диапазон, который содержит выделение).  
  
 Если элемент управления "ползунок" содержит стиль TBS_ENABLESELRANGE, пользователь может выбрать диапазон смежных значений из него. Ряд функций-членов разрешить диапазон выбора для настраиваться динамически. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) функция-член задает начальный и конечный позиции выделения. После завершения установки диапазон выбора пользователя приложения могут получить параметры с помощью [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) функции-члена. Чтобы очистить Выбор пользователя, используйте [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Использование CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

