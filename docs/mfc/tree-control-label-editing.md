---
title: Меток древовидного элемента управления редактирования | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d665ae37bfc843fc2ab0f24fe4489b76935e62d2
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956269"
---
# <a name="tree-control-label-editing"></a>Редактирование меток древовидного элемента управления
Пользователь непосредственно изменять метки составляющих элементов в виде дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), содержащее **TVS_EDITLABELS** стиля. Пользователь начинает изменения, щелкнув подпись элемента, который находится в фокусе. Приложение начинает редактирования с помощью [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) функции-члена. Дерево отправляет уведомления при изменении начинается и когда оно отменено или завершено. По завершении редактирования вы отвечаете за обновление метки элемента при необходимости.  
  
 Когда метка начинается редактирование, отправляет дерево [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) сообщение уведомления. С помощью обработки этого уведомления, можно разрешить изменение некоторые метки и запрещают его изменение других. Возвращается значение 0 разрешает изменение, и возвращает ненулевое значение, блокируется.  
  
 Когда редактирование меток отменено или завершено, дерево отправляет [TVN_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) сообщение уведомления. *LParam* параметр — адрес [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) структуры. **Элемент** член является [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) структура, которая определяет элемент и включает в себя измененного текста. Вы несете ответственность за обновление элемента метки, при необходимости возможно после проверки измененной строки. *PszText* членом `TV_ITEM` равно 0, если изменение отменяется.  
  
 Во время редактирование меток, обычно в ответ на [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) сообщение уведомления, можно получить указатель на поле редактирования, используемый для редактирования метки с помощью [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) члена функция. Можно вызвать поле редактирования [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) функции-члена для ограничения объема текста, пользователь может ввести или подкласс поле редактирования перехват и отменить недопустимые символы. Тем не менее, отображается ли элемент управления для редактирования только *после* **TVN_BEGINLABELEDIT** отправляется.  
  
## <a name="see-also"></a>См. также  
 [Использование CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

