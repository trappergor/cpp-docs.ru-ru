---
title: Структура COLORADJUSTMENT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03c5346a59ea52ca6b2428652d5da69aacf6ea5b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849099"
---
# <a name="coloradjustment-structure"></a>Структура COLORADJUSTMENT
`COLORADJUSTMENT` Структура определяет значение коррекции цвета, используемые Windows `StretchBlt` и `StretchDIBits` функции при `StretchBlt` режим — ПОЛУТОНОВЫЕ.  
  
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
 Указывает, каким образом следует подготовить изображения вывода. Этот член может быть присвоено значение NULL или любое сочетание следующих значений:  
  
- CA_NEGATIVE указывает, что должно отображаться исходного изображения с противоположным знаком.  
  
- CA_LOG_FILTER указывает, что логарифмической функции должен применяться для окончательного плотность цвета выходные данные. Это увеличит контрастность при низкой освещенности.  
  
 *caIlluminantIndex*  
 Указывает освещенности источника света, под которой просматривается объекта изображения. Этот член может быть присвоено одно из следующих значений:  
  
- ILLUMINANT_EQUAL_ENERGY  
  
- ILLUMINANT_A  
  
- ILLUMINANT_B  
  
- ILLUMINANT_C  
  
- ILLUMINANT_D50  
  
- ILLUMINANT_D55  
  
- ILLUMINANT_D65  
  
- ILLUMINANT_D75  
  
- ILLUMINANT_F2  
  
- ILLUMINANT_TURNGSTEN  
  
- ILLUMINANT_DAYLIGHT  
  
- ILLUMINANT_FLUORESCENT  
  
- ILLUMINANT_NTSC  
  
 *caRedGamma*  
 Задает значение гамма коррекции n-й power для красного первичной исходные цвета. Значение должно быть в диапазоне от 2500 до 65,000. Значение 10 000 означает не гамма коррекции.  
  
 *caGreenGamma*  
 Задает значение гамма коррекции n-й питания для сервера-источника зеленого цветов источника. Значение должно быть в диапазоне от 2500 до 65,000. Значение 10 000 означает не гамма коррекции.  
  
 *caBlueGamma*  
 Задает значение гамма коррекции n-й питания для синего основного цвета источника. Значение должно быть в диапазоне от 2500 до 65,000. Значение 10 000 означает не гамма коррекции.  
  
 *caReferenceBlack*  
 Указывает ссылку по черного цвета источника. Цвета, которые темнее, чем это рассматриваются как черный. Значение должно быть в диапазоне от 0 до 4 000.  
  
 *caReferenceWhite*  
 Указывает ссылку на белый для исходные цвета. Цвета, которые светлее, чем это рассматриваются как белый. Значение должно быть в диапазоне от 6000 до 10 000.  
  
 *caContrast*  
 Уровень контрастности для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает, что корректировка контрастности.  
  
 *caBrightness*  
 Указывает значение яркости для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает, что не яркости.  
  
 *caColorfulness*  
 Указывает объем colorfulness для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает, что не colorfulness коррекции.  
  
 *caRedGreenTint*  
 Указывает объем красный или зеленый оттенок коррекции для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Положительные числа бы настройте на красный, а отрицательные числа также к зеленый. Значение 0 означает, что корректировка оттенок.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


