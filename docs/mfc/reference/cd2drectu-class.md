---
title: "Класс CD2DRectU | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU class
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
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
ms.openlocfilehash: 74c05d7f4be9b9308cdcb2b91a0455a4cd025dc1
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectu-class"></a>Класс CD2DRectU
Программа-оболочка для `D2D1_RECT_U`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|Перегружен. Создает `CD2DRectU` объекта из `D2D1_RECT_U` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectU::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, содержит ли выражение недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|Преобразует `CD2DRectU` для `CRect` объектов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
 Создает объект CD2DRectU из CRect объекта.  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `rect`  
 исходного прямоугольника.  
  
 `uLeft`  
 Левая координата источника  
  
 `uTop`  
 Верхняя координата источника  
  
 `uRight`  
 Источник прямо координат  
  
 `uBottom`  
 Нижняя координата источника  
  
##  <a name="isnull"></a>CD2DRectU::ISNULL  
 Возвращает логическое значение, указывающее, содержит ли выражение недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если прямоугольника верхней, левой, нижней и правильные значения все равно 0; в противном случае — значение FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectU::operator CRect  
 Преобразует CD2DRectU CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение D2D прямоугольника.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

