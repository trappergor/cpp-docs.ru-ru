---
title: Информация об изображениях в списках изображений образе | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98bc629cde74cf7a6fc8a416de862f50a1dd5ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422289"
---
# <a name="image-information-in-image-lists"></a>Сведения об изображениях в списках изображений

[CImageList](../mfc/reference/cimagelist-class.md) включает ряд функций, получающих сведения из списка изображений. [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) заполняет функция-член `IMAGEINFO` структуру сведениями о одно изображение, включая маркеры и маскировал точечные рисунки, число цветовых плоскостей и бит на пиксель и ограничивающий прямоугольник изображения в растрового изображения. Эти сведения можно использовать для прямого управления для изображения, точечные рисунки.

[GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) функция-член возвращает число изображений в списке изображений.

Можно создать на основе изображения и маски, в списке изображений с помощью значка [функции ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) функция-член. Функция возвращает дескриптор значок "Создать".

## <a name="see-also"></a>См. также

[Использование CImageList](../mfc/using-cimagelist.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

