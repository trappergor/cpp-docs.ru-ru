---
title: Использование списка изображений
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: cb95de134939e1b06e2a8b827424c986f8c48ef3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180470"
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
