---
title: Использование списка изображений | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dc30d418ae57205e4566dad7f490a773321768e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391674"
---
# <a name="using-an-image-list"></a>Использование списка изображений

Типичное использование списка изображений соответствует шаблону ниже:

- Создать [CImageList](../mfc/reference/cimagelist-class.md) объекта и вызвать одну из перегрузок его [создать](../mfc/reference/cimagelist-class.md#create) функции для создания списка изображений и присоединить его к `CImageList` объекта.

- Если не добавить изображения, при создании списка изображений, добавление изображений в списке изображений, вызвав [добавить](../mfc/reference/cimagelist-class.md#add) или [чтения](../mfc/reference/cimagelist-class.md#read) функция-член.

- Связать список изображений с элементом управления путем вызова функции-члена этого элемента управления или рисование изображений из списка изображений, самостоятельно, используя список изображений [рисования](../mfc/reference/cimagelist-class.md#draw) функция-член.

- Возможно, позволяют пользователю перетаскивать изображения, с помощью встроенной поддержки списка изображений для перетаскивания.

> [!NOTE]
>  Если при создании списка изображений **новый** оператор, вы должны уничтожить `CImageList` объекта, когда вы закончите с ним.

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

