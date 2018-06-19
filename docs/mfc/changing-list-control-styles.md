---
title: Изменение стилей элемента управления списка | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9d93511ad4f4ca835e09b6eaa3f612f0888e844
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344846"
---
# <a name="changing-list-control-styles"></a>Изменение стилей элемента управления "Список"
Можно изменить стиль окна элемента управления списка ([CListCtrl](../mfc/reference/clistctrl-class.md)) в любое время после его создания. Можно изменить стиль окна, измените тип представления, используемого элементом управления. Например, для эмуляции обозревателя, можно предоставить пункты меню или кнопок панели инструментов для переключения управления между различными представлениями: значков, представление списка и т. д.  
  
 Например, когда пользователь выбирает элемент меню, можно внести вызов [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) для получения текущего стиля элемента управления, а затем вызвать [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) сбросить стиль. Дополнительные сведения см. в разделе [с использованием элементов управления представления списка](http://msdn.microsoft.com/library/windows/desktop/bb774736) в Windows SDK.  
  
 Доступные стили, перечислены в [создать](../mfc/reference/clistctrl-class.md#create). Стили `LVS_ICON`, `LVS_SMALLICON`, `LVS_LIST`, и `LVS_REPORT` указать четыре списки управления.  
  
## <a name="extended-styles"></a>Расширенные стили  
 Кроме стандартных стилей для элемента управления list есть другой набор, называют расширенные стили. Эти стили, рассматриваемые в [расширенных стилей представления списка](http://msdn.microsoft.com/library/windows/desktop/bb774732) в Windows SDK, обеспечивают разнообразные полезные возможности настройки поведения элемента управления списка. Чтобы реализовать поведение определенного стиля (например, выбор при наведении указателя мыши), вызвать [CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), передав необходимые стиль. В следующем примере демонстрируется вызов функции:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]  
  
> [!NOTE]
>  Выбор при наведении указателя мыши для работы, вы также должны иметь либо **LVS_EX_ONECLICKACTIVATE** или **LVS_EX_TWOCLICKACTIVATE** включен.  
  
## <a name="see-also"></a>См. также  
 [Использование CListCtrl](../mfc/using-clistctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

