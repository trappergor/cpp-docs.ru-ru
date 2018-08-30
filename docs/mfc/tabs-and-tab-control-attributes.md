---
title: Вкладки и вкладке управлять атрибутами | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02f939c9f9314f3e24921879836c2743ae7d5ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223286"
---
# <a name="tabs-and-tab-control-attributes"></a>Вкладки и атрибуты элемента управления "Вкладка"
У вас есть много возможностей управления внешним видом и поведением вкладок, составляющих набор вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Каждая вкладка может содержать метку, значок, состоянии элемент и значение 32-разрядных определяемые приложением, связанные с ней. Для каждой вкладки можно отобразить значок и метку.  
  
 Кроме того, каждый элемент вкладки может иметь три состояния: нажата, ненажатое или выделенным. Это состояние может устанавливаться только путем изменения существующего элемента вкладки. Для изменения существующего элемента вкладки, получить с помощью вызова [GetItem](../mfc/reference/ctabctrl-class.md#getitem), изменить `TCITEM` структуры (в частности *dwState* и *dwStateMask* данные-члены ), а затем возвращают измененный `TCITEM` структуры с помощью вызова [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Если необходимо очистить состояния элементов из всех элементов вкладки в `CTabCtrl` объекта, вызовите [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Эта функция сбрасывает состояние объекта все вкладки или все элементы за исключением выделенного.  
  
 Следующий код удаляет состояние все элементы вкладок и затем изменяет состояние третий элемент:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 Дополнительные сведения о вкладке атрибутов, см. в разделе [вкладки и атрибуты "Вкладка"](/windows/desktop/Controls/tab-controls) в пакете Windows SDK. Дополнительные сведения о Добавление вкладок в элемент управления вкладками, см. в разделе [Добавление вкладок в элемент управления вкладки](../mfc/adding-tabs-to-a-tab-control.md) далее в этом разделе.  
  
## <a name="see-also"></a>См. также  
 [Использование CTabCtrl](../mfc/using-ctabctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

