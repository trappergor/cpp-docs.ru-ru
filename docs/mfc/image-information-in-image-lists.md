---
title: Сведения об изображениях в списках изображений
ms.date: 11/04/2016
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
ms.openlocfilehash: c12198c769585763095d22b73d11f7af3c9d6fc0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624498"
---
# <a name="image-information-in-image-lists"></a>Сведения об изображениях в списках изображений

[CImageList](reference/cimagelist-class.md) включает ряд функций, которые извлекают информацию из списка изображений. Функция-член [жетимажеинфо](reference/cimagelist-class.md#getimageinfo) заполняет `IMAGEINFO` структуру сведениями об отдельном изображении, включая маркеры точечных рисунков изображения и маски, число цветовых плоскостей и бит на пиксель, а также ограничивающий прямоугольник изображения в точечном рисунке изображения. Эти сведения можно использовать для непосредственного управления точечными рисунками изображения.

Функция члена [жетимажекаунт](reference/cimagelist-class.md#getimagecount) извлекает количество изображений в списке изображений.

Вы можете создать значок на основе изображения и маски в списке изображений с помощью функции члена [екстрактикон](reference/cimagelist-class.md#extracticon) . Функция возвращает маркер нового значка.

## <a name="see-also"></a>См. также раздел

[Использование CImageList](using-cimagelist.md)<br/>
[Элементы управления](controls-mfc.md)
