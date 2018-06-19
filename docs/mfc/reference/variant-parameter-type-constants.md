---
title: Константы типа параметра Variant | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13820ff4fb07c3743f36ba3ebe33ee56a3a79c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379864"
---
# <a name="variant-parameter-type-constants"></a>Константы типа параметра Variant
В этом разделе перечислены новые константы, указывающие типы variant параметр предназначен для работы с классы элементов управления OLE, библиотеки классов Microsoft Foundation.  
  
 Ниже приведен список констант класса:  
  
##  <a name="_mfc_variant_data_constants"></a> Variant-константы данных  
  
-   **VTS_COLOR** 32-разрядное целое число, используемое для представления значения цвета RGB.  
  
-   **VTS_FONT** указатель **IFontDisp** интерфейс шрифта OLE-объекта.  
  
-   **VTS_HANDLE** значением дескриптора Windows.  
  
-   **VTS_PICTURE** указатель `IPictureDisp` интерфейса OLE-объекта изображения.  
  
-   **VTS_OPTEXCLUSIVE** 16-разрядное значение, используемое для элемента управления, который предназначен для использования в группе управления, такие как переключателей. Этот тип указывает контейнеру, что если один из элемента управления в группу имеет **TRUE** значение, все остальные должно быть **FALSE**.  
  
-   **VTS_TRISTATE** 16-разрядное знаковое целое число используется для свойств, которые может принимать одно из трех возможных значений (выбранные, снят, недоступен), например, типа "флажок".  
  
-   **VTS_XPOS_HIMETRIC** 32-разрядное целое число без знака, используемый для представления положение по оси x в **HIMETRIC** единицы.  
  
-   **VTS_YPOS_HIMETRIC** 32-разрядное целое число без знака, используемый для представления положение по оси y в **HIMETRIC** единицы.  
  
-   **VTS_XPOS_PIXELS** 32-разрядное целое число без знака, используемый для представления позиция по оси x в пикселях.  
  
-   **VTS_YPOS_PIXELS** 32-разрядное целое число без знака, используемый для представления позиция по оси y в пикселях.  
  
-   **VTS_XSIZE_PIXELS** 32-разрядное целое число без знака, используемый для представления ширину объекта экрана в пикселях.  
  
-   **VTS_YSIZE_PIXELS** 32-разрядное целое число без знака, используемый для представления высоту объекта экрана в пикселях.  
  
-   **VTS_XSIZE_HIMETRIC** 32-разрядное целое число без знака, используемый для представления ширину объекта на экране в **HIMETRIC** единицы.  
  
-   **VTS_YSIZE_HIMETRIC** 32-разрядное целое число без знака, используемый для представления высоту объекта на экране в **HIMETRIC** единицы.  
  
    > [!NOTE]
    >  Дополнительные variant константы определены для всех типов variant, за исключением элемента **VTS_FONT** и **VTS_PICTURE**, обеспечивающие указатель co данных variant nstant. Эти константы именуются **VTS_P** `constantname` соглашение. Например **VTS_PCOLOR** — это указатель на **VTS_COLOR** константой.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
