---
title: "Глобальные функции преобразования пикселей HIMETRIC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efb7e7da896aea4e377225f4c1e2c9948e635705
ms.lasthandoff: 02/24/2017

---
# <a name="pixelhimetric-conversion-global-functions"></a>Глобальные функции преобразования пикселей или HIMETRIC
Эти функции обеспечивают поддержку преобразования в и из пикселей и единицы HIMETRIC.  
  
> [!IMPORTANT]
>  Функции, перечисленные в следующей таблице, не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Преобразует HIMETRIC (каждая единица равна 0,01 мм) в пикселях.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Преобразует пиксели в единицы HIMETRIC (каждая единица равна 0,01 мм).|  
  
##  <a name="a-nameatlhimetrictopixela--atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
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
 [!code-cpp[NVC_ATL_COM №&49;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  
  
##  <a name="a-nameatlpixeltohimetrica--atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
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
 [!code-cpp[NVC_ATL_COM №&51;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Требования  
 **Заголовок:** atlwin.h  

## <a name="see-also"></a>См. также  
 [Функции](../../atl/reference/atl-functions.md)

