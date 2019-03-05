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
ms.openlocfilehash: b15a303f69ce13cf3ba3b6c1c0739acdb8a33c7c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261639"
---
# <a name="variant-parameter-type-constants"></a>Константы типа параметра Variant

В этом разделе перечислены новые константы, указывающие типы variant параметров, разработанном для использования с классы элементов управления OLE, библиотеки классов Microsoft Foundation.

Ниже приведен список констант класса:

##  <a name="_mfc_variant_data_constants"></a> Variant-константы данных

- VTS_COLOR 32-разрядное целочисленное значение, используемое для представления значения цвета RGB.

- Указатель типа VTS_FONT `IFontDisp` интерфейс OLE-объекта шрифта.

- Значение дескриптора VTS_HANDLE Windows.

- Указатель типа VTS_PICTURE `IPictureDisp` интерфейс рисунок OLE-объекта.

- VTS_OPTEXCLUSIVE 16-разрядное значение, используемое для элемента управления, который предназначен для использования в группе элементов управления, например для переключателей. Этот тип указывает контейнеру, что если один элемент управления в группе имеет значение TRUE, все остальные должен иметь значение FALSE.

- VTS_TRISTATE 16-разрядное целочисленное значение, используемое для свойств, которые могут иметь одно из трех возможных значений (выбранный, снят, недоступным), например, типа "флажок".

- VTS_XPOS_HIMETRIC 32-разрядное целое число без знака используется для представления позиции по оси x в единицах HIMETRIC.

- VTS_YPOS_HIMETRIC 32-разрядное целое число без знака используется для представления позиции по оси y в единицах HIMETRIC.

- VTS_XPOS_PIXELS 32-разрядное целое число без знака используется для представления позиции по оси x в пикселях.

- VTS_YPOS_PIXELS 32-разрядное целое число без знака используется для представления позиции по оси y в пикселях.

- VTS_XSIZE_PIXELS 32-разрядное целое число без знака используется для представления ширину объект экрана в пикселях.

- VTS_YSIZE_PIXELS 32-разрядное целое число без знака используется для представления высоту объект экрана в пикселях.

- VTS_XSIZE_HIMETRIC 32-разрядное целое число без знака используется для представления ширина в единицах HIMETRIC объекта на экране.

- VTS_YSIZE_HIMETRIC 32-разрядное целое число без знака используется для представления высота в единицах HIMETRIC объекта на экране.

    > [!NOTE]
    >  Дополнительные variant константы определены для всех вариантов типов, за исключением VTS_FONT и VTS_PICTURE, которые обеспечивают указатель на константу данных variant. Эти константы, именуются с помощью VTS_P`constantname` соглашение. Например VTS_PCOLOR является указателем на vts_color-константа.

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
