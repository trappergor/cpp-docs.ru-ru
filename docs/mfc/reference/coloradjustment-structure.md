---
title: Структура COLORADJUSTMENT | Документы Microsoft
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
ms.openlocfilehash: ffb0ec0233edd968ad121b84f9e1d584a26f3387
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369968"
---
# <a name="coloradjustment-structure"></a>Структура COLORADJUSTMENT
`COLORADJUSTMENT` Структура определяет значение коррекции цвета, используемые Windows `StretchBlt` и **StretchDIBits** функции при `StretchBlt` режим — **ПОЛУТОНОВОЙ**.  
  
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
 Указывает, каким образом следует подготовить изображения вывода. Этот член может быть присвоено **NULL** или любое сочетание следующих значений:  
  
- **CA_NEGATIVE** задает отображение исходный образ с противоположным знаком.  
  
- **CA_LOG_FILTER** Включение применения логарифмической функции для окончательного плотность цвета выходных данных. Это увеличит контрастность при низкой освещенности.  
  
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
 Задает значение гамма коррекции n-й питания для red основного источника цветов. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caGreenGamma*  
 Задает значение гамма коррекции n-й питания для зеленый основного источника цветов. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caBlueGamma*  
 Задает значение гамма коррекции n-й питания для синего основного цвета источника. Значение должно быть в диапазоне от 2 500 до 65,000. Значение 10 000 означает гамма-коррекцию.  
  
 *caReferenceBlack*  
 Указывает ссылку на черного цвета источника. Цвета, которые темнее, чем это рассматриваются как черный. Значение должно быть в диапазоне от 0 до 4 000.  
  
 *caReferenceWhite*  
 Указывает ссылку на белого цвета источника. Цвета, которые светлее, чем это рассматриваются как пустое. Значение должно быть в диапазоне от 6000 до 10 000.  
  
 *caContrast*  
 Указывает значение яркости для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает отсутствие подстройки контрастности.  
  
 *caBrightness*  
 Указывает значение яркости для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает отсутствие подстройки яркости.  
  
 *caColorfulness*  
 Указывает объем colorfulness для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Значение 0 означает отсутствие подстройки colorfulness.  
  
 *caRedGreenTint*  
 Указывает объем красный или зеленый оттенок коррекции для применения к исходному объекту. Значение должно быть в диапазоне от -100 до 100. Положительные числа бы настроить сторону красный и отрицательные числа измените сторону зеленый. Значение 0 означает отсутствие подстройки оттенок.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


