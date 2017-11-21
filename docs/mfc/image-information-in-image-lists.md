---
title: "Сведения в списках изображений изображения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CImageList class [MFC], image information in
- image lists [MFC], image information in
ms.assetid: 73c41543-fa91-405d-b15b-0feffa6a72c1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 80e897ec79314abb2e77864e53d470e72f275a94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="image-information-in-image-lists"></a>Сведения об изображениях в списках изображений
[CImageList](../mfc/reference/cimagelist-class.md) включает ряд функций, которые извлекают данные о из списка изображений. [GetImageInfo](../mfc/reference/cimagelist-class.md#getimageinfo) заполняет функция-член `IMAGEINFO` структуры со сведениями о одно изображение, включая маркеры изображения и маска точечные рисунки, число цветовых плоскостей и бита на пиксель и ограничивающий прямоугольник изображения в битовой карты изображения. Эти сведения можно использовать для прямого управления для изображения, точечные рисунки.  
  
 [GetImageCount](../mfc/reference/cimagelist-class.md#getimagecount) функция-член возвращает число изображений в списке изображений.  
  
 Можно создать на основе образа и маски в список изображений с помощью значка [ExtractIcon](../mfc/reference/cimagelist-class.md#extracticon) функции-члена. Функция возвращает дескриптор нового значка.  
  
## <a name="see-also"></a>См. также  
 [Использование CImageList](../mfc/using-cimagelist.md)   
 [Элементы управления](../mfc/controls-mfc.md)

