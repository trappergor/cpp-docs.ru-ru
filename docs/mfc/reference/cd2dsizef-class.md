---
title: "Класс CD2DSizeF | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeF class
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f780dc919f102023f2bd524fa69e73e76feec02b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsizef-class"></a>Класс CD2DSizeF
Программа-оболочка для D2D1_SIZE_F.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DSizeF : public D2D1_SIZE_F;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Перегружен. Создает `CD2DSizeF` объекта из `D2D1_SIZE_F` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeF::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, содержит ли выражение недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeF::operator CSize](#operator_csize)|Преобразует `CD2DSizeF` для `CSize` объектов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_SIZE_F`  
  
 [CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2dsizef"></a>CD2DSizeF::CD2DSizeF  
 Создает объект CD2DSizeF из CSize объекта.  
  
```  
CD2DSizeF(const CSize& size);  
CD2DSizeF(const D2D1_SIZE_F& size);  
  CD2DSizeF(const D2D1_SIZE_F* size);

 
CD2DSizeF(
    FLOAT cx = 0.,  
    FLOAT cy = 0.);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Размер источника  
  
 `cx`  
 исходная ширина  
  
 `cy`  
 Исходная высота  
  
##  <a name="isnull"></a>CD2DSizeF::ISNULL  
 Возвращает логическое значение, указывающее, содержит ли выражение недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ширина и Высота пустой. в противном случае — значение FALSE.  
  
##  <a name="operator_csize"></a>CD2DSizeF::operator CSize  
 Преобразует CD2DSizeF CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение размера D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)

