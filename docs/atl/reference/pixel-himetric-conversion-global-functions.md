---
title: Глобальные функции преобразования пикселей в единицы HIMETRIC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5ab980813eec09fe0eef35f54280444d8c08b80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105393"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования пикселей/HIMETRIC

Эти функции обеспечивают поддержку преобразования в и из пикселей и единицах HIMETRIC.

> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Преобразует пиксели единицах HIMETRIC (каждая единица равна 0,01 мм).|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Преобразует пиксели в единицы HIMETRIC (каждая единица равна 0,01 мм).|

##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel

Преобразует размер объекта в единицах HIMETRIC (каждая единица равна 0,01 мм) в размер в пикселях на экране устройства.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric, 
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Параметры

*lpSizeInHiMetric*<br/>
[in] Указатель на размер объекта в единицах HIMETRIC.

*lpSizeInPix*<br/>
[out] Указатель, на которой должен возвращаться размер объекта в пикселях.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="atlpixeltohimetric"></a>  AtlPixelToHiMetric

Преобразует размер объекта в пикселях на экране устройства в единицы HIMETRIC (каждая единица равна 0,01 мм).

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Параметры

*lpSizeInPix*<br/>
[in] Указатель на размер объекта в пикселях.

*lpSizeInHiMetric*<br/>
[out] Где размер объекта в единицах HIMETRIC будет возвращаться указатель.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h  

## <a name="see-also"></a>См. также

[Функции](../../atl/reference/atl-functions.md)
