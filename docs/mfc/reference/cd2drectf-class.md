---
title: "Класс CD2DRectF | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DRectF
- CD2DRectF
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF class
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
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
ms.openlocfilehash: 5bca2dcce32679083e5917d855f711984989a489
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectf-class"></a>Класс CD2DRectF
Программа-оболочка для `D2D1_RECT_F`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|Перегружен. Создает `CD2DRectF` объекта из `D2D1_RECT_F` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, содержит ли выражение недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|Преобразует `CD2DRectF` для `CRect` объектов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="a-namecd2drectfa--cd2drectfcd2drectf"></a><a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
 Создает объект CD2DRectF из CRect объекта.  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 исходного прямоугольника.  
  
 `fLeft`  
 Левая координата источника  
  
 `fTop`  
 Верхняя координата источника  
  
 `fRight`  
 Источник прямо координат  
  
 `fBottom`  
 Нижняя координата источника  
  
##  <a name="a-nameisnulla--cd2drectfisnull"></a><a name="isnull"></a>CD2DRectF::ISNULL  
 Возвращает логическое значение, указывающее, содержит ли выражение недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если прямоугольника верхней, левой, нижней и правильные значения все равно 0; в противном случае — значение FALSE.  
  
##  <a name="a-nameoperatorcrecta--cd2drectfoperator-crect"></a><a name="operator_crect"></a>CD2DRectF::operator CRect  
 Преобразует CD2DRectF CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение D2D прямоугольника.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

