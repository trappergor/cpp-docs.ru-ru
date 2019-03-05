---
title: Сведения об изображениях в списках изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: 7b83b7e5f7de6f8ccca95d732f71a5d73a97e943
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263069"
---
# <a name="image-information-in-image-lists"></a>Сведения об изображениях в списках изображений

[CImageList](../mfc/reference/cimagelist-class.md) включает ряд функций, получающих сведения из списка изображений. [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) заполняет функция-член `IMAGEINFO` структуру сведениями о одно изображение, включая маркеры и маскировал точечные рисунки, число цветовых плоскостей и бит на пиксель и ограничивающий прямоугольник изображения в растрового изображения. Эти сведения можно использовать для прямого управления для изображения, точечные рисунки.

[GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) функция-член возвращает число изображений в списке изображений.

Можно создать на основе изображения и маски, в списке изображений с помощью значка [функции ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) функция-член. Функция возвращает дескриптор значок "Создать".

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
