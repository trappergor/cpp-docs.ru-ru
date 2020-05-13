---
title: Использование списка изображений
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 0d9566739a15e5d216eb052a7265313850515648
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366578"
---
# <a name="using-an-image-list"></a>Использование списка изображений

Типичное использование списка изображений следует шаблону ниже:

- Создайте объект [CImageList](../mfc/reference/cimagelist-class.md) и вызоводно одной из перегрузок функции [Создания,](../mfc/reference/cimagelist-class.md#create) `CImageList` чтобы создать список изображений и прикрепить его к объекту.

- Если вы не добавляли изображения при создании списка изображений, добавляйте изображения в список изображений, позвонив в [функцию Add](../mfc/reference/cimagelist-class.md#add) или [Read.](../mfc/reference/cimagelist-class.md#read)

- Связать список изображений с элементом управления, позвонив соответствующую функцию элемента этого элемента управления, или нарисовать изображения из списка изображений самостоятельно, используя функцию [члена](../mfc/reference/cimagelist-class.md#draw) списка изображений.

- Возможно, позвольте пользователю перетащить изображение, используя встроенную поддержку списка изображений для перетаскивания.

> [!NOTE]
> Если список изображений **new** был создан с новым `CImageList` оператором, вы должны уничтожить объект, когда вы закончите с ним.

## <a name="see-also"></a>См. также раздел

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
