---
title: Управление списками изображений
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: cb7376241febd6bd1545cd183147e14a15313820
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622462"
---
# <a name="manipulating-image-lists"></a>Управление списками изображений

Функция-член [Replace](reference/cimagelist-class.md#replace) заменяет изображение в списке изображений ([CImageList](reference/cimagelist-class.md)) новым изображением. Эта функция также полезна, если необходимо динамически увеличивать количество образов в объекте списка изображений. Функция [сетимажекаунт](reference/cimagelist-class.md#setimagecount) динамически изменяет число образов, хранящихся в списке изображений. При увеличении размера списка изображений вызовите, `Replace` чтобы добавить изображения в новые слоты изображений. При уменьшении размера списка изображений освобождаются изображения, размер которых превышает новый.

Функция [удаления](reference/cimagelist-class.md#remove) члена удаляет изображение из списка изображений. Функция элемента [Copy](reference/cimagelist-class.md#copy) позволяет копировать или переключать изображения в списке изображений. Эта функция позволяет указать, следует ли копировать исходный образ в целевой индекс, иначе исходные и конечные образы должны быть заменены.

Чтобы создать новый список изображений путем слияния двух списков изображений, используйте подходящую перегрузку функции [создания](reference/cimagelist-class.md#create) члена. Эта перегрузка `Create` объединяет первое изображение существующих списков изображений, сохраняя полученный образ в новом объекте списка изображений. Новый образ создается путем рисования второго изображения прозрачно на первом. Маска для нового изображения является результатом выполнения операции логического или в битах масок для двух существующих изображений.

Это повторяется до тех пор, пока все изображения не будут объединены и добавлены в новый объект списка изображений.

Вы можете записать сведения об образе в архив, вызвав функцию [записи](reference/cimagelist-class.md#write) члена и прочтите ее обратно, вызвав функцию члена [Read](reference/cimagelist-class.md#read) .

Функции элементов [жетсафехандле](reference/cimagelist-class.md#getsafehandle), [attach](reference/cimagelist-class.md#attach)и [Detach](reference/cimagelist-class.md#detach) позволяют управлять маркером списка изображений, присоединенного к `CImageList` объекту, а функция члена [делетеимажелист](reference/cimagelist-class.md#deleteimagelist) удаляет список изображений без удаления `CImageList` объекта.

## <a name="see-also"></a>См. также раздел

[Использование CImageList](using-cimagelist.md)<br/>
[Элементы управления](controls-mfc.md)
