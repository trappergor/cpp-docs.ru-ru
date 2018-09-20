---
title: Уничтожение элемента управления списка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls [MFC], destroying
- CListCtrl class [MFC], destroying controls
ms.assetid: 513ec820-3a02-49d2-b073-a6a7a3fc91b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25642357e3dd9117ae2817307ed5fa3c4a0921d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424547"
---
# <a name="destroying-the-list-control"></a>Уничтожение элемента управления "Список"

При внедрении вашей [CListCtrl](../mfc/reference/clistctrl-class.md) объект как член данных класса представления или диалогового окна, он уничтожается при уничтожении его владельцем. Если вы используете [CListView](../mfc/reference/clistview-class.md), платформа уничтожает элемент управления, когда она окончательно удаляет представление.

Если упорядочить для некоторых данных списка для сохранения в приложение, а не в элементе управления списком, необходимо упорядочить для его освобождения. Дополнительные сведения см. в разделе [элементы обратного вызова и маска обратного вызова](/windows/desktop/Controls/using-list-view-controls) в пакете Windows SDK.

Кроме того вы несете ответственность за освобождение любые списки изображений, вы создали и связанный с объектом элемента управления списка.

## <a name="see-also"></a>См. также

[Использование CListCtrl](../mfc/using-clistctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

