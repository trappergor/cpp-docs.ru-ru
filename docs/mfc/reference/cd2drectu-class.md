---
title: "Класс CD2DRectU | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs: C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2bf261f31f470862a506466a8815daef796743f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cd2drectu-class"></a>Класс CD2DRectU
Программа-оболочка для `D2D1_RECT_U`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|Перегружен. Создает `CD2DRectU` объекта из `D2D1_RECT_U` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DRectU::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, является ли выражение содержит недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|Преобразует `CD2DRectU` для `CRect` объекта.|  
  
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
 исходного прямоугольника  
  
 `uLeft`  
 Координата левой источника  
  
 `uTop`  
 Координата верхней источника  
  
 `uRight`  
 Источник справа координат  
  
 `uBottom`  
 Нижняя координата источника  
  
##  <a name="isnull"></a>CD2DRectU::ISNULL  
 Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если верхней прямоугольника, левую, нижнюю и правильные значения, все равно 0; в противном случае — значение FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectU::operator CRect  
 Преобразует CD2DRectU CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение прямоугольника D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
