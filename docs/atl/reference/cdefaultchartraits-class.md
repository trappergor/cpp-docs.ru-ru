---
title: "Класс CDefaultCharTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATL::CDefaultCharTraits<T>
- ATL.CDefaultCharTraits
- ATL.CDefaultCharTraits<T>
- ATL::CDefaultCharTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 12991cfcf1ac96808a0315899d01ce3012324dc6
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultchartraits-class"></a>Класс CDefaultCharTraits
Этот класс предоставляет два статических функций для преобразования символов в верхний или нижний регистр.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(Статический) Эта функция вызывается для преобразования символа в верхний регистр.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Статический) Эта функция вызывается для преобразования символа в нижний регистр.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет функции, которые используются классом [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-namechartolowera--cdefaultchartraitschartolower"></a><a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 Эта функция вызывается для преобразования символа в нижний регистр.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Знак для преобразования в нижний регистр.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#132;](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="a-namechartouppera--cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 Эта функция вызывается для преобразования символа в верхний регистр.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 Знак для преобразования в верхний регистр.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

