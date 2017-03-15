---
title: "Структура COLORADJUSTMENT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7f88877fa009abf4e811ba0a99b7e0e1683f998a
ms.lasthandoff: 02/24/2017

---
# <a name="coloradjustment-structure"></a>Структура COLORADJUSTMENT
`COLORADJUSTMENT` Структура определяет значения коррекции цвета, используемые Windows `StretchBlt` и **StretchDIBits** функции при `StretchBlt` режим **ПОЛУТОНОВОЙ**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD caSize;  
    WORD caFlags;  
    WORD caIlluminantIndex;  
    WORD caRedGamma;  
    WORD caGreenGamma;  
    WORD caBlueGamma;  
    WORD caReferenceBlack;  
    WORD caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### <a name="parameters"></a>Параметры  
 *caSize*  
 Задает размер структуры в байтах.  
  
 *caFlags*  
 Указывает, как следует подготовить образ выходные данные. Этот член может быть присвоен **NULL** или любое сочетание следующих значений:  
  
- **CA_NEGATIVE** задает отображение отрицательной исходного изображения.  
  
- **CA_LOG_FILTER** Включение применения логарифмической функция окончательный плотности цвета выходные данные. Это приведет к увеличению контрастность при низкой освещенности.  
  
 *caIlluminantIndex*  
 Указывает яркости источника света, под которой просматривается объект изображения. Этот член может быть присвоено одно из следующих значений:  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 Задает значение гамма коррекции n-й power red первичного источника цветов. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caGreenGamma*  
 Задает значение гамма коррекции n-й питания для зеленого основного источника цветов. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caBlueGamma*  
 Задает значение гамма коррекции синего основного цвета источника питания n-й. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caReferenceBlack*  
 Указывает ссылку на черный для цветов исходного. Цвета, которые темнее, чем это рассматриваются как черный. Значение должно быть в диапазоне от 0 до 4 000.  
  
 *caReferenceWhite*  
 Указывает ссылку на белый для исходного цвета. Цвета, которые светлее, чем это рассматриваются как белый. Значение должно быть в диапазоне от 6000 до 10 000.  
  
 *caContrast*  
 Указывает значение яркости для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает отсутствие подстройки контрастности.  
  
 *caBrightness*  
 Указывает значение яркости для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает без корректировки яркости.  
  
 *caColorfulness*  
 Указывает объем colorfulness для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает отсутствие подстройки colorfulness.  
  
 *caRedGreenTint*  
 Указывает объем корректировки красный или зеленый оттенок для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Настраивает положительных чисел на красный и отрицательные числа измените на зеленый. 0 означает отсутствие подстройки оттенок.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)



