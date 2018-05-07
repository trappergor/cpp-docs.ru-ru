---
title: Класс CD2DSizeU | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa7c42216f55479050812b559f533829d55162b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dsizeu-class"></a>Класс CD2DSizeU
Программа-оболочка для D2D1_SIZE_U.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Перегружен. Создает `CD2DSizeU` объекта из `D2D1_SIZE_U` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeU::ISNULL](#isnull)|Возвращает `boolean` значение, указывающее, является ли выражение содержит недопустимые данные ( `null`).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](#operator_csize)|Преобразует `CD2DSizeU` для `CSize` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxrendertarget.h  
  
##  <a name="cd2dsizeu"></a>  CD2DSizeU::CD2DSizeU  
 Создает объект CD2DSizeU из CSize объекта.  
  
```  
CD2DSizeU(const CSize& size);  
CD2DSizeU(const D2D1_SIZE_U& size);  
  CD2DSizeU(const D2D1_SIZE_U* size);

 
CD2DSizeU(
    UINT32 cx = 0,  
    UINT32 cy = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `size`  
 Размер источника  
  
 `cx`  
 исходная ширина  
  
 `cy`  
 Высота источника  
  
##  <a name="isnull"></a>  CD2DSizeU::ISNULL  
 Возвращает логическое значение, указывающее, является ли выражение содержит недопустимые данные (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если ширина и Высота пустой. в противном случае — значение FALSE.  
  
##  <a name="operator_csize"></a>  CD2DSizeU::operator CSize  
 Преобразует CD2DSizeU CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее значение размера D2D.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../mfc/reference/mfc-classes.md)
