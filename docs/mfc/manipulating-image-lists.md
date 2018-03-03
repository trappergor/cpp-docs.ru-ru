---
title: "Управление списками изображений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c2670f3935e2f4c482728000a268cb46cc9dbdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manipulating-image-lists"></a>Управление списками изображений
[Заменить](../mfc/reference/cimagelist-class.md#replace) функция-член заменяет изображение в список изображений ([CImageList](../mfc/reference/cimagelist-class.md)) заменяется новым изображением. Эта функция также полезна, если необходимо динамически увеличить число образов в объекте списка изображений. [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) функция динамически изменяет количество изображений, хранящихся в списке изображений. При увеличении размера списка изображений, вызовите **заменить** для добавления изображения в новый образ слоты. При уменьшении размера списка изображений, освобождаются изображения за пределами нового размера.  
  
 [Удалить](../mfc/reference/cimagelist-class.md#remove) функция-член удаляет изображение из списка изображений. [Копирования](../mfc/reference/cimagelist-class.md#copy) функция-член можно скопировать или замены изображений в списке изображений. Эта функция позволяет показать исходного изображения должны копироваться в конечный индекс или перестановке исходного и конечного изображений.  
  
 Чтобы создать новый список изображений путем слияния двух списков изображений, используйте соответствующую перегрузку [создать](../mfc/reference/cimagelist-class.md#create) функции-члена. Эта перегрузка **создать** слияний первое изображение существующий образ перечислены хранение результирующий образ в новый объект списка изображений. Новый образ создается путем рисования второе изображение прозрачно на первый. Маска для нового образа — результат выполнения логической операции или на биты маски для двух существующих образов.  
  
 Повторяется, пока все образы, объединяются и добавляются в новый объект списка изображений.  
  
 Можно написать информации об изображении в архив, вызвав [записи](../mfc/reference/cimagelist-class.md#write) функции-члена и чтение его обратно, вызвав [чтения](../mfc/reference/cimagelist-class.md#read) функции-члена.  
  
 [GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [присоединение](../mfc/reference/cimagelist-class.md#attach), и [отсоединения](../mfc/reference/cimagelist-class.md#detach) функции-члены можно управлять дескриптор списка изображений, присоединенные к `CImageList` объекта, пока [DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) функция-член Удаляет список изображений без потерь `CImageList` объекта.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

