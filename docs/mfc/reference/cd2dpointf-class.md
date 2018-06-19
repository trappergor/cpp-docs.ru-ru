---
title: Класс CD2DPointF | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a6439a25072975d28b98e4c6d88c3a1de8703d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348710"
---
# <a name="cd2dpointf-class"></a>Класс CD2DPointF
Программа-оболочка для `D2D1_POINT_2F`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Перегружен. Создает `CD2DPointF` объекта из `D2D1_POINT_2F` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|Преобразует `CD2DPointF` для `CPoint` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>  CD2DPointF::CD2DPointF  
 Создает объект CD2DPointF из объекта класса CWnd.  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>Параметры  
 `pt`  
 Исходная точка  
  
 `fX`  
 Источник X  
  
 `fY`  
 Источник Y  
  
##  <a name="operator_cpoint"></a>  CD2DPointF::operator CPoint  
 Преобразует CD2DPointF CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение точки D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
