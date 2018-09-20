---
title: Сведения об элементе управления дерева | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a61d6dbf2084288d6015e8fc2c08bfc2283d4ba4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391024"
---
# <a name="tree-control-item-information"></a>Сведения об элементе древовидного элемента управления

Элементы управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) имеют ряд функций-членов, которые получают сведения об элементах в элементе управления. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) функция-член извлекает часть или все данные, связанные с элементом. Эти данные могут включать текст элемента, состояние, изображения, количество дочерних элементов и определяемые приложением значение 32-разрядной. Имеется также [SetItem](../mfc/reference/ctreectrl-class.md#setitem) функцию, которая может установить некоторые или все данные, связанные с элементом.

[GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), и [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) функции-члены извлечения отдельных атрибутов элемент. Каждая из этих функций имеет соответствующую функцию набор для настройки атрибутов элемента.

[GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) функция-член извлекает элемента управления дерева, содержащего указанную связь с текущим элементом. Эту функцию можно получить родительского элемента, следующий или предыдущий элемент видимым, первый дочерний элемент и т. д. Существуют также функции-члены для прохода по дереву: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [Getselecteditem класса](../mfc/reference/ctreectrl-class.md#getselecteditem), и [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem).

[GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) функция-член извлекает ограничивающий прямоугольник для элемента управления дерева. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) и [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) функции-члены получить число элементов в виде дерева и количество элементов, которые видимы в настоящий момент в окне дерева элемента управления, соответственно. Убедитесь, что какой-либо элемент является видимым, вызвав [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) функция-член.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

