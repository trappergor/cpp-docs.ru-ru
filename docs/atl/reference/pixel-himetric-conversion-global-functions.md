---
title: Глобальные функции преобразования «пиксель-HIMETRIC»
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 43a12985f259603a9b67f22f7a7891bf847c0b0f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78862938"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования пикселей и HIMETRIC

Эти функции обеспечивают поддержку преобразования в Пиксели и HIMETRIC единицы измерения.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, нельзя использовать в приложениях, выполняемых в среда выполнения Windows.

|||
|-|-|
|[атлхиметриктопиксел](#atlhimetrictopixel)|Преобразует единицы HIMETRIC (каждая единица — 0,01 мм) в пиксели.|
|[атлпикселтохиметрик](#atlpixeltohimetric)|Преобразует Пиксели в HIMETRIC единицы (каждая единица — 0,01 мм).|

##  <a name="atlhimetrictopixel"></a>атлхиметриктопиксел

Преобразует размер объекта в единицах HIMETRIC (каждая единица равна 0,01 мм) в размер в пикселях на экране устройства.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Параметры

*лпсизеинхиметрик*<br/>
окне Указатель на размер объекта в единицах HIMETRIC.

*лпсизеинпикс*<br/>
заполняет Указатель на место, где должен возвращаться размер объекта в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

##  <a name="atlpixeltohimetric"></a>атлпикселтохиметрик

Преобразует размер объекта в пикселях на экране устройства в единицы HIMETRIC (каждая единица равна 0,01 мм).

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Параметры

*лпсизеинпикс*<br/>
окне Указатель на размер объекта в пикселях.

*лпсизеинхиметрик*<br/>
заполняет Указатель на место, где должен возвращаться размер объекта в единицах HIMETRIC.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
