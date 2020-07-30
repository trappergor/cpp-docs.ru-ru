---
title: Использование списка изображений
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: 710831ea8ef6b52292ba3e8eb84a69575c6c7508
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226832"
---
# <a name="using-an-image-list"></a>Использование списка изображений

Типичное использование списка изображений соответствует шаблону, приведенному ниже.

- Создайте объект [CImageList](../mfc/reference/cimagelist-class.md) и вызовите одну из перегрузок его функции [CREATE](../mfc/reference/cimagelist-class.md#create) , чтобы создать список изображений и присоединить его к `CImageList` объекту.

- Если вы не добавили образы при создании списка образов, добавьте изображения в список изображений, вызвав функцию [добавления](../mfc/reference/cimagelist-class.md#add) или [чтения](../mfc/reference/cimagelist-class.md#read) члена.

- Свяжите список изображений с элементом управления, вызвав соответствующую функцию-член этого элемента управления или нарисуйте изображения из списка изображений самостоятельно с помощью функции-члена [Draw](../mfc/reference/cimagelist-class.md#draw) в списке изображений.

- Возможно, пользователь может перетащить изображение, используя встроенную поддержку перетаскивания списка изображений.

> [!NOTE]
> Если список изображений был создан с помощью **`new`** оператора, то `CImageList` при завершении его создания необходимо уничтожить объект.

## <a name="see-also"></a>См. также статью

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
