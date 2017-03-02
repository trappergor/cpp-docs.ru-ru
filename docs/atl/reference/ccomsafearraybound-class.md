---
title: "Класс CComSafeArrayBound | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComSafeArrayBound
- ATL::CComSafeArrayBound
- CComSafeArrayBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
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
ms.openlocfilehash: 1cc2adef85c902b7ad12b152b35a7ef68e6abacb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafearraybound-class"></a>Класс CComSafeArrayBound
Этот класс является оболочкой для [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>Члены  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|Конструктор.|  
|[GetCount](#getcount)|Этот метод используется для возврата числа элементов.|  
|[GetLowerBound](#getlowerbound)|Этот метод используется для возврата нижняя граница.|  
|[GetUpperBound](#getupperbound)|Этот метод используется для возврата верхней границы.|  
|[SetCount](#setcount)|Этот метод используется для указания числа элементов.|  
|[SetLowerBound](#setlowerbound)|Вызовите этот метод, чтобы установить нижнюю границу.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Наборы `CComSafeArrayBound` новое значение.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является оболочкой для **SAFEARRAYBOUND** структура, используемая [класса CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для создания запросов и верхнюю и нижнюю границы одного измерения `CComSafeArray` объекта и количество элементов, которые он содержит. Многомерный массив `CComSafeArray` объекта используется массив `CComSafeArrayBound` , по одному для каждого измерения. Таким образом при использовании методов, таких как [GetCount](#getcount), имейте в виду, что этот метод не возвращает общее число элементов в многомерном массиве.  
  
 **Заголовок:** atlsafe.h  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsafe.h  
  
##  <a name="a-nameccomsafearraybounda--ccomsafearrayboundccomsafearraybound"></a><a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
 Конструктор.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ulCount`  
 Количество элементов в массиве.  
  
 `lLowerBound`  
 Нижняя граница с номерами массива.  
  
### <a name="remarks"></a>Примечания  
 Если массив имеет должен осуществляться из программы на Visual C++, рекомендуется, нижняя граница определяется как 0. Возможно, следует использовать значение другая нижняя граница, если в массиве для использования в других языках, таких как Visual Basic.  
  
##  <a name="a-namegetcounta--ccomsafearrayboundgetcount"></a><a name="getcount"></a>CComSafeArrayBound::GetCount  
 Этот метод используется для возврата числа элементов.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов.  
  
### <a name="remarks"></a>Примечания  
 Если связанный `CComSafeArray` многомерного массива представляет объект, этот метод будет возвращать только общее число элементов в самой правой размерности. Используйте [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) получить общее число элементов.  
  
##  <a name="a-namegetlowerbounda--ccomsafearrayboundgetlowerbound"></a><a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 Этот метод используется для возврата нижняя граница.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нижнюю границу `CComSafeArrayBound` объекта.  
  
##  <a name="a-namegetupperbounda--ccomsafearrayboundgetupperbound"></a><a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 Этот метод используется для возврата верхней границы.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает верхнюю границу `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Верхний предел зависит от числа элементов и значение нижней границы. Например если количество элементов равно 10, нижняя граница — 0, верхняя граница будет автоматически устанавливаться на 9.  
  
##  <a name="a-nameoperatoreqa--ccomsafearrayboundoperator-"></a><a name="operator_eq"></a>CComSafeArrayBound::operator =  
 Наборы `CComSafeArrayBound` новое значение.  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `bound`  
 Объект `CComSafeArrayBound`.  
  
 `ulCount`  
 Количество элементов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `CComSafeArrayBound` объект.  
  
### <a name="remarks"></a>Примечания  
 `CComSafeArrayBound` Объектов можно назначить с помощью существующего `CComSafeArrayBound`, или указав число элементов, в которых регистр нижняя граница имеет значение 0 по умолчанию.  
  
##  <a name="a-namesetcounta--ccomsafearrayboundsetcount"></a><a name="setcount"></a>CComSafeArrayBound::SetCount  
 Этот метод используется для указания числа элементов.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ulCount`  
 Количество элементов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов в `CComSafeArrayBound` объекта.  
  
##  <a name="a-namesetlowerbounda--ccomsafearrayboundsetlowerbound"></a><a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
 Вызовите этот метод, чтобы установить нижнюю границу.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lLowerBound`  
 Нижняя граница.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новый нижняя граница `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если массив имеет должен осуществляться из программы на Visual C++, рекомендуется, нижняя граница определяется как 0. Возможно, следует использовать значение другая нижняя граница, если в массиве для использования в других языках, таких как Visual Basic.  
  
 Верхний предел зависит от числа элементов и значение нижней границы. Например если количество элементов равно 10, нижняя граница — 0, верхняя граница будет автоматически устанавливаться на 9.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

