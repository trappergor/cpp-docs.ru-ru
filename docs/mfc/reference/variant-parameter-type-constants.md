---
title: "Константы типа параметра Variant | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
- VTS_XPOS_HIMETRIC constant
- VTS_FONT constant
- VTS_XPOS_PIXELS constant
- VTS_COLOR constant
- Variants
- VTS_YPOS_PIXELS constant
- VTS_YSIZE_HIMETRIC constant
- VTS_YPOS_HIMETRIC constant
- Variants, parameter type constants
- Variant data constants
- VTS_PICTURE constant
- VTS_TRISTATE constant
- VTS_XSIZE_HIMETRIC constant
- VTS_HANDLE constant
- VTS_XSIZE_PIXELS constant
- VTS_OPTEXCLUSIVE constant
- VTS_YSIZE_PIXELS constant
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3b09357859b8fc87252fba704de8f2a927981873
ms.lasthandoff: 02/24/2017

---
# <a name="variant-parameter-type-constants"></a>Константы типа параметра Variant
В этом разделе перечислены новые константы, указывающие типы variant параметр предназначен для использования с классы элементов управления OLE, библиотеки классов Microsoft Foundation.  
  
 Ниже приведен список констант класса:  
  
##  <a name="a-namemfcvariantdataconstantsa-variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>Variant-константы данных  
  
-   **VTS_COLOR** 32-разрядное целое число со знаком, используемое для представления значения цветов RGB.  
  
-   **VTS_FONT** указатель **IFontDisp** интерфейс OLE-объекта шрифта.  
  
-   **VTS_HANDLE** значение дескриптора окна.  
  
-   **VTS_PICTURE** указатель `IPictureDisp` интерфейс рисунок OLE-объекта.  
  
-   **VTS_OPTEXCLUSIVE** 16-разрядное значение, используемое для элемента управления, который предназначен для использования в группе управления, такие как переключатели. Этот тип указывает контейнеру, что если один из элемента управления в группе имеет **TRUE** значение, все остальные должно быть **FALSE**.  
  
-   **VTS_TRISTATE** 16-разрядное целое число со знаком используется для свойств, которые может принимать одно из трех возможных значений (выбранного снят, недоступен), например, поле с флажком.  
  
-   **VTS_XPOS_HIMETRIC** 32-разрядное целое число без знака, используемое для представления положения по оси x в **HIMETRIC** единиц.  
  
-   **VTS_YPOS_HIMETRIC** 32-разрядное целое число без знака, используемое для представления положения по оси y в **HIMETRIC** единиц.  
  
-   **VTS_XPOS_PIXELS** 32-разрядное целое число без знака, используемое для представления положения по оси x в пикселях.  
  
-   **VTS_YPOS_PIXELS** 32-разрядное целое число без знака, используемое для представления положения по оси y в пикселях.  
  
-   **VTS_XSIZE_PIXELS** 32-разрядное целое число без знака, используемый для представления Ширина объекта экрана в пикселях.  
  
-   **VTS_YSIZE_PIXELS** 32-разрядное целое число без знака, используемый для представления высоту объекта экрана в пикселях.  
  
-   **VTS_XSIZE_HIMETRIC** 32-разрядное целое число без знака, используемый для представления ширину объекта на экране в **HIMETRIC** единиц.  
  
-   **VTS_YSIZE_HIMETRIC** 32-разрядное целое число без знака, используемый для представления высоту объекта на экране в **HIMETRIC** единиц.  
  
    > [!NOTE]
    >  Дополнительные variant константы определены для всех типов variant, за исключением класса **VTS_FONT** и **VTS_PICTURE**, обеспечивающие указатель константы данных variant. Эти константы именуются **VTS_P** `constantname` соглашение. Например **VTS_PCOLOR** — это указатель на **VTS_COLOR** константой.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

