---
title: Управление списками изображений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eeccfa5245c6395e530859eb91c7f9a5c01335e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930375"
---
# <a name="manipulating-image-lists"></a>Управление списками изображений
[Заменить](../mfc/reference/cimagelist-class.md#replace) функция-член заменяет изображение в список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) заменяется новым изображением. Эта функция также полезна, если необходимо динамически увеличить число образов в объекте списка изображений. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) функция динамически изменяет количество изображений, хранящихся в списке изображений. При увеличении размера списка изображений, вызовите `Replace` для добавления изображения в новый образ слоты. При уменьшении размера списка изображений, освобождаются изображения за пределами нового размера.  
  
 [Удалить](../mfc/reference/cimagelist-class.md#remove) функция-член удаляет изображение из списка изображений. [Копирования](../mfc/reference/cimagelist-class.md#copy) функция-член можно скопировать или замены изображений в списке изображений. Эта функция позволяет показать исходного изображения должны копироваться в конечный индекс или перестановке исходного и конечного изображений.  
  
 Чтобы создать новый список изображений путем слияния двух списков изображений, используйте соответствующую перегрузку [создать](../mfc/reference/cimagelist-class.md#create) функции-члена. Эта перегрузка `Create` слияний первое изображение существующий образ перечислены хранение результирующий образ в новый объект списка изображений. Новый образ создается путем рисования второе изображение прозрачно на первый. Маска для нового образа — результат выполнения логической операции или на биты маски для двух существующих образов.  
  
 Повторяется, пока все образы, объединяются и добавляются в новый объект списка изображений.  
  
 Можно написать информации об изображении в архив, вызвав [записи](../mfc/reference/cimagelist-class.md#write) функции-члена и чтение его обратно, вызвав [чтения](../mfc/reference/cimagelist-class.md#read) функции-члена.  
  
 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [присоединение](../mfc/reference/cimagelist-class.md#attach), и [отсоединения](../mfc/reference/cimagelist-class.md#detach) функции-члены можно управлять дескриптор списка изображений, присоединенные к `CImageList` объекта, пока [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) функция-член Удаляет список изображений без потерь `CImageList` объекта.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

