---
title: Константы типа параметра Variant
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: f73c72830216679f8a91d0037d48c1e1b8e400c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372868"
---
# <a name="variant-parameter-type-constants"></a>Константы типа параметра Variant

В этой теме перечислены новые константы, указывающие типы параметров вариантов, предназначенные для использования с классами управления OLE в библиотеке класса Microsoft Foundation.

Ниже приводится список констант класса:

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>Вариант константы данных

- VTS_COLOR 32-битный ряд, используемый для представления значения цвета RGB.

- VTS_FONT указатель на `IFontDisp` интерфейс объекта шрифта OLE.

- VTS_HANDLE значение ручки Windows.

- VTS_PICTURE указатель на `IPictureDisp` интерфейс объекта изображения OLE.

- VTS_OPTEXCLUSIVE 16-битное значение, используемое для управления, предназначенное для использования в группе элементов управления, таких как радиокнопки. Этот тип говорит контейнеру, что если один элемент управления в группе имеет истинное значение, все остальные должны быть FALSE.

- VTS_TRISTATE 16-битный подписанный ряд, используемый для свойств, которые могут иметь одно из трех возможных значений (выбранных, очищенных, недоступных), например, флажок.

- VTS_XPOS_HIMETRIC 32-битный неподписанный ряд, используемый для представления положения вдоль оси x в единицах HIMETRIC.

- VTS_YPOS_HIMETRIC 32-битный неподписанный ряд, используемый для представления положения вдоль оси y в единицах HIMETRIC.

- VTS_XPOS_PIXELS 32-битный неподписанный ряд, используемый для представления положения вдоль оси x в пикселях.

- VTS_YPOS_PIXELS 32-битный неподписанный ряд, используемый для представления положения вдоль оси y в пикселях.

- VTS_XSIZE_PIXELS 32-битный неподписанный ряд, используемый для представления ширины объекта экрана в пикселях.

- VTS_YSIZE_PIXELS 32-битный неподписанный ряд, используемый для представления высоты объекта экрана в пикселях.

- VTS_XSIZE_HIMETRIC 32-битный неподписанный ряд, используемый для представления ширины объекта экрана в единицах HIMETRIC.

- VTS_YSIZE_HIMETRIC 32-битный неподписанный ряд, используемый для представления высоты объекта экрана в единицах HIMETRIC.

    > [!NOTE]
    >  Для всех типов вариантов определены дополнительные константы вариантов, за исключением VTS_FONT и VTS_PICTURE, которые обеспечивают указатель к константу данных варианта. Эти константы названы с помощью VTS_P`constantname` конвенции. Например, VTS_PCOLOR является указателем на константу VTS_COLOR.

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
