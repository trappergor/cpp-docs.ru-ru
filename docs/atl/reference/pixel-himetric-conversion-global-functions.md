---
title: Глобальные функции преобразования Pixel-HIMETRIC
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 08c72c0d8f3d061950d6945d9fb412c0a16355da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326142"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования Pixel/HIMETRIC

Эти функции обеспечивают поддержку для преобразования в и из пикселей и HIMETRIC единиц.

> [!IMPORTANT]
> Функции, перечисленные в следующей таблице, не могут использоваться в приложениях, выполняемых в Windows Runtime.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Преобразует единицы HIMETRIC (каждая единица составляет 0,01 миллиметра) в пиксели.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Преобразует пиксели в единицы HIMETRIC (каждая единица составляет 0,01 миллиметра).|

## <a name="atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel

Преобразует размер объекта в единицах HIMETRIC (каждая единица равна 0,01 мм) в размер в пикселях на экране устройства.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Параметры

*lpsizeinhimetric*<br/>
(в) Указатель на размер объекта в единицах HIMETRIC.

*lpSizeinpix*<br/>
(ваут) Указатель на то, где размер объекта в пикселях должен быть возвращен.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric

Преобразует размер объекта в пикселях на экране устройства в единицы HIMETRIC (каждая единица равна 0,01 мм).

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Параметры

*lpSizeinpix*<br/>
(в) Указатель на размер объекта в пикселях.

*lpsizeinhimetric*<br/>
(ваут) Указатель на место, где должен быть возвращен размер объекта в единицах HIMETRIC.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="see-also"></a>См. также раздел

[Функции](../../atl/reference/atl-functions.md)
