---
title: Управление списками изображений
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: 1e86961980c91ade47a3d6510dec5c04ac36cffb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304851"
---
# <a name="manipulating-image-lists"></a>Управление списками изображений

[Замените](../mfc/reference/cimagelist-class.md#replace) функция-член заменяет изображение в списке изображений ([CImageList](../mfc/reference/cimagelist-class.md)) с помощью нового образа. Эта функция также полезна, если необходимо динамически увеличить число изображений в объекте списка изображений. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) функции динамически изменяет количество изображений, хранящихся в списке изображений. Если вы увеличите размер списка изображений, вызовите `Replace` для добавления картинок в новый образ слотов. При уменьшении размера списка изображений, освобождаются образов за пределами новый размер.

[Удалить](../mfc/reference/cimagelist-class.md#remove) функция-член удаляет изображение из списка изображений. [Копирования](../mfc/reference/cimagelist-class.md#copy) функция-член можно скопировать или замены изображений в списке изображений. Эта функция позволяет указать исходное изображение должны копироваться в конечный индекс ли заменяться образы источника и назначения.

Чтобы создать список изображений путем слияния двух списков изображений, используйте соответствующую перегрузку [создать](../mfc/reference/cimagelist-class.md#create) функция-член. Эта перегрузка `Create` слияний, перечислены первое изображение из существующего образа, хранение результирующий образ в новый объект списка изображений. Новый образ создается путем рисования второе изображение прозрачно отказа в первую очередь. Маска для нового образа является результатом выполнения операции логического или на биты маски для двух существующих образов.

Повторяется, пока все образы, объединяются и добавляются в новый объект списка изображений.

Можно написать информации об изображении в архив, вызвав [записи](../mfc/reference/cimagelist-class.md#write) функция-член и считывать их обратно, вызвав [чтения](../mfc/reference/cimagelist-class.md#read) функция-член.

[GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [Attach](../mfc/reference/cimagelist-class.md#attach), и [отсоединения](../mfc/reference/cimagelist-class.md#detach) функции-члены можно управлять дескриптор списка изображений, подключенный к `CImageList` объекта, пока [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) функция-член Удаляет список изображений без потерь `CImageList` объекта.

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
