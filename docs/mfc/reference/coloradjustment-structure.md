---
title: "Структура COLORADJUSTMENT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLORADJUSTMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLORADJUSTMENT - структура"
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура COLORADJUSTMENT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `COLORADJUSTMENT` определяет значения коррекции цвета, используемые Windows `StretchBlt` и функциями **StretchDIBits**, когда режим `StretchBlt`**HALFTONE**.  
  
## Синтаксис  
  
```  
  
      typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD  caSize;  
    WORD  caFlags;  
    WORD  caIlluminantIndex;  
    WORD  caRedGamma;  
    WORD  caGreenGamma;  
    WORD  caBlueGamma;  
    WORD  caReferenceBlack;  
    WORD  caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### Параметры  
 *caSize*  
 Определяет размер структуры в байтах.  
  
 *caFlags*  
 Указывает, как изображение вывода должен быть подготовлен.  Этот элемент можно задать значение **NULL** или сочетанию любое из следующих значений:  
  
-   **CA\_NEGATIVE** указывает, что у исходного изображения должен быть открыт.  
  
-   **CA\_LOG\_FILTER** указывает, что логарифмическая функция должна быть применена к окончательной плотности цветов.  Это приводит к увеличению цветов контраст при яркость незначительны.  
  
 *caIlluminantIndex*  
 Определяет яркость источника света в которых объект изображения просмотреть.  Этот элемент можно задать одно из следующих значений:  
  
-   **ILLUMINANT\_EQUAL\_ENERGY**  
  
-   **ILLUMINANT\_A**  
  
-   **ILLUMINANT\_B**  
  
-   **ILLUMINANT\_C**  
  
-   **ILLUMINANT\_D50**  
  
-   **ILLUMINANT\_D55**  
  
-   **ILLUMINANT\_D65**  
  
-   **ILLUMINANT\_D75**  
  
-   **ILLUMINANT\_F2**  
  
-   **ILLUMINANT\_TURNGSTEN**  
  
-   **ILLUMINANT\_DAYLIGHT**  
  
-   **ILLUMINANT\_FLUORESCENT**  
  
-   **ILLUMINANT\_NTSC**  
  
 *caRedGamma*  
 Определяет элемент последовательности гамма\-коррекцию значение состояния для красного цвета основного источника.  Значение должно быть в диапазоне от 2,500 до 65,000.  Значение 10,000 означает не имеет гамма\-коррекцию.  
  
 *caGreenGamma*  
 Определяет элемент последовательности гамма\-коррекцию значение состояния для зеленого цветов основного источника.  Значение должно быть в диапазоне от 2,500 до 65,000.  Значение 10,000 означает не имеет гамма\-коррекцию.  
  
 *caBlueGamma*  
 Определяет элемент последовательности гамма\-коррекцию значение для синего цветов степени основной источника.  Значение должно быть в диапазоне от 2,500 до 65,000.  Значение 10,000 означает не имеет гамма\-коррекцию.  
  
 *caReferenceBlack*  
 Определяет черную ссылку для цветов источника.  Все цвета, темне, чем это обрабатываются с черным.  Значение должно быть в диапазоне от 0 до 4,000.  
  
 *caReferenceWhite*  
 Определяет белую ссылку для цветов источника.  Все цвета, которые имеют более чем это рассматриваться как white.  Значение должно быть в диапазоне от 6,000 до 10,000.  
  
 *caContrast*  
 Задает вертикальный контрастности, чтобы применить к исходному объекту.  Значение должно быть в диапазоне от \-100 до 100.  Значение 0 означает не имеет корректировку контрастности.  
  
 *caBrightness*  
 Задает вертикальный яркости, чтобы применить к исходному объекту.  Значение должно быть в диапазоне от \-100 до 100.  Значение 0 означает не имеет корректировку яркости.  
  
 *caColorfulness*  
 Задает объем colorfulness, чтобы применить к исходному объекту.  Значение должно быть в диапазоне от \-100 до 100.  Значение 0 означает не имеет colorfulness корректировка.  
  
 *caRedGreenTint*  
 Задает объем красной, зеленой коррекции оттенка, чтобы применить к исходному объекту.  Значение должно быть в диапазоне от \-100 до 100.  Положительные числа отрегулировали бы к красному отрицательные числа. настройка зеленый.  0 Означает не имеет корректировку оттенка.  
  
## Требования  
 **Header:** wingdi.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)