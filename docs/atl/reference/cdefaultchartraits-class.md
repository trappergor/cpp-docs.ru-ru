---
title: "Класс CDefaultCharTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs: C++
helpviewer_keywords: CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 02595c426a631e15bf2f1b5baed2550a8befe20a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdefaultchartraits-class"></a>Класс CDefaultCharTraits
Этот класс предоставляет два статические функции для преобразования символов в верхний или нижний регистр.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Статический) Вызывайте эту функцию для преобразования в верхний регистр символа.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Статический) Вызывайте эту функцию для преобразования символа в нижний регистр.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет функции, используемые классом [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 Вызывайте эту функцию для преобразования символа в нижний регистр.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Знак, который необходимо преобразовать в нижний регистр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 Вызывайте эту функцию для преобразования в верхний регистр символа.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Знак, который необходимо преобразовать в верхний регистр.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
