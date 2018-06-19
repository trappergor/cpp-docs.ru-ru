---
title: Глобальные функции преобразования пикселей HIMETRIC | Документы Microsoft
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
ms.openlocfilehash: 92d84204bdf02e75f1baf64bd52d96eab0b3d271
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359430"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования пикселей/HIMETRIC
Эти функции предоставляют поддержку для преобразования из точек и единицах HIMETRIC.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Преобразует единицах HIMETRIC (каждая единица равна 0,01 мм) в пикселях.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Преобразует пиксели в единицах HIMETRIC (каждая единица равна 0,01 мм).|  
  
##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel  
 Преобразует размер объекта в единицах HIMETRIC (каждая единица равна 0,01 мм) в размер в пикселях на экране устройства.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>Параметры  
 `lpSizeInHiMetric`  
 [in] Указатель на размер объекта в единицах HIMETRIC.  
  
 `lpSizeInPix`  
 [out] Указатель, где должен быть возвращен размер объекта в пикселях.  
  
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
 `lpSizeInPix`  
 [in] Указатель на размер объекта в пикселях.  
  
 `lpSizeInHiMetric`  
 [out] Указатель, где должен быть возвращен размер объекта в единицах HIMETRIC.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)
