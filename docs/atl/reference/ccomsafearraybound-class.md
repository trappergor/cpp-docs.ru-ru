---
title: Класс CComSafeArrayBound | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb0acc5059fa76531421cb261cb1d640aef3709
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954343"
---
# <a name="ccomsafearraybound-class"></a>Класс CComSafeArrayBound
Этот класс является оболочкой для [SAFEARRAYBOUND](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound) структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|Конструктор.|  
|[GetCount](#getcount)|Этот метод используется для возврата количества элементов.|  
|[GetLowerBound](#getlowerbound)|Вызовите этот метод для возврата нижняя граница.|  
|[GetUpperBound](#getupperbound)|Вызовите этот метод для возврата верхней границы.|  
|[SetCount](#setcount)|Вызовите этот метод, чтобы задать число элементов.|  
|[SetLowerBound](#setlowerbound)|Этот метод используется для задания нижняя граница.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Наборы `CComSafeArrayBound` новое значение.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является оболочкой для `SAFEARRAYBOUND` структуру, используемую [CComSafeArray](../../atl/reference/ccomsafearray-class.md). Он предоставляет методы для создания запросов и верхней и нижней границы одного измерения из `CComSafeArray` объект и число элементов, которые он содержит. Многомерный массив `CComSafeArray` объект использует массив `CComSafeArrayBound` , по одному для каждого измерения. Таким образом при использовании методов, таких как [GetCount](#getcount), имейте в виду, что этот метод не возвращает общее число элементов в многомерном массиве.  
  
 **Заголовок:** atlsafe.h  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound  
 Конструктор.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *Инициализирует метод ulCount*  
 Количество элементов в массиве.  
  
 *lLowerBound*  
 Нижняя граница, из которого нумеруется массива.  
  
### <a name="remarks"></a>Примечания  
 Если массив должен быть предоставлен доступ из программы Visual C++, рекомендуется, что нижняя граница быть определен как 0. Возможно, следует использовать значение другая нижняя граница, если нужно использовать с другими языками, например Visual Basic.  
  
##  <a name="getcount"></a>  CComSafeArrayBound::GetCount  
 Этот метод используется для возврата количества элементов.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число элементов.  
  
### <a name="remarks"></a>Примечания  
 Если связанный `CComSafeArray` представляет многомерный массив, этот метод будет возвращать только общее число элементов в измерении крайний правый. Используйте [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) получить общее число элементов.  
  
##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound  
 Вызовите этот метод для возврата нижняя граница.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нижнюю границу `CComSafeArrayBound` объекта.  
  
##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound  
 Вызовите этот метод для возврата верхней границы.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает верхнюю границу `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Верхняя граница зависит от количества элементов и значение нижней границы. Например если нижняя граница — 0 и количество элементов равно 10, верхняя граница будет автоматически устанавливаться на 9.  
  
##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =  
 Наборы `CComSafeArrayBound` новое значение.  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *привязан*  
 Объект `CComSafeArrayBound`.  
  
 *Инициализирует метод ulCount*  
 Количество элементов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на `CComSafeArrayBound` объект.  
  
### <a name="remarks"></a>Примечания  
 `CComSafeArrayBound` Объект можно назначить с помощью существующего `CComSafeArrayBound`, или указав число элементов, в которых случае нижняя граница имеет значение 0 по умолчанию.  
  
##  <a name="setcount"></a>  CComSafeArrayBound::SetCount  
 Вызовите этот метод, чтобы задать число элементов.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *Инициализирует метод ulCount*  
 Количество элементов  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество элементов в `CComSafeArrayBound` объекта.  
  
##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound  
 Этот метод используется для задания нижняя граница.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lLowerBound*  
 Нижняя граница.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает новое значение нижней границы из `CComSafeArrayBound` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если массив должен быть предоставлен доступ из программы Visual C++, рекомендуется, что нижняя граница быть определен как 0. Возможно, следует использовать значение другая нижняя граница, если нужно использовать с другими языками, например Visual Basic.  
  
 Верхняя граница зависит от количества элементов и значение нижней границы. Например если нижняя граница — 0 и количество элементов равно 10, верхняя граница будет автоматически устанавливаться на 9.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
