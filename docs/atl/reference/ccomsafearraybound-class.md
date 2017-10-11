---
title: "Класс CComSafeArrayBound | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 01198e8de5f2eb1cbe0787bd287820d222875c20
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
|[GetLowerBound](#getlowerbound)|Этот метод используется для получения нижней границы.|  
|[GetUpperBound](#getupperbound)|Этот метод используется для возврата верхней границы.|  
|[SetCount](#setcount)|Этот метод используется для указания числа элементов.|  
|[SetLowerBound](#setlowerbound)|Этот метод используется для задания нижняя граница.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Наборы `CComSafeArrayBound` новое значение.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является оболочкой для **SAFEARRAYBOUND** структура, используемая [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для создания запросов и верхняя и нижняя границы одно измерение `CComSafeArray` объекта и количество элементов, которые он содержит. Многомерный массив `CComSafeArray` объект использует массив `CComSafeArrayBound` объектов, по одному для каждого измерения. Таким образом при использовании методов, таких как [GetCount](#getcount), имейте в виду, что этот метод не возвращает общее число элементов в многомерном массиве.  
  
 **Заголовок:** atlsafe.h  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>CComSafeArrayBound::CComSafeArrayBound  
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
 Если массив должен быть получен из программы Visual C++, рекомендуется, нижняя граница определяется как 0. Часто бывает предпочтительнее использовать другая нижняя граница значение, если в массиве для использования с другими языками, например Visual Basic.  
  
##  <a name="getcount"></a>CComSafeArrayBound::GetCount  
 Этот метод используется для возврата числа элементов.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов.  
  
### <a name="remarks"></a>Примечания  
 Если связанный `CComSafeArray` представляет многомерного массива, этот метод будет возвращать только общее число элементов в крайнее правое измерение. Используйте [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) получить общее число элементов.  
  
##  <a name="getlowerbound"></a>CComSafeArrayBound::GetLowerBound  
 Этот метод используется для получения нижней границы.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нижнюю границу `CComSafeArrayBound` объекта.  
  
##  <a name="getupperbound"></a>CComSafeArrayBound::GetUpperBound  
 Этот метод используется для возврата верхней границы.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает верхнюю границу `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Верхняя граница зависит от количества элементов и значение нижней границы. Например если количество элементов равно 10, нижняя граница — 0, верхняя граница будет автоматически задан до 9.  
  
##  <a name="operator_eq"></a>CComSafeArrayBound::operator =  
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
 `CComSafeArrayBound` Объект можно назначить с помощью существующей `CComSafeArrayBound`, или указав число элементов, в которых регистр нижняя граница имеет значение 0 по умолчанию.  
  
##  <a name="setcount"></a>CComSafeArrayBound::SetCount  
 Этот метод используется для указания числа элементов.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `ulCount`  
 Количество элементов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов в `CComSafeArrayBound` объекта.  
  
##  <a name="setlowerbound"></a>CComSafeArrayBound::SetLowerBound  
 Этот метод используется для задания нижняя граница.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lLowerBound`  
 Нижняя граница.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новый нижняя граница `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если массив должен быть получен из программы Visual C++, рекомендуется, нижняя граница определяется как 0. Часто бывает предпочтительнее использовать другая нижняя граница значение, если в массиве для использования с другими языками, например Visual Basic.  
  
 Верхняя граница зависит от количества элементов и значение нижней границы. Например если количество элементов равно 10, нижняя граница — 0, верхняя граница будет автоматически задан до 9.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

