---
title: "Операторы &lt;system_error&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 82f7876aca66524ba50b1e01b74437d8a2117976
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-operators"></a>Операторы &lt;system_error&gt;
||||  
|-|-|-|  
|[оператор!=](#operator_neq)|[оператор&lt;](#operator_lt_)|[оператор==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  оператор==  
 Проверяет равенство объекта слева от оператора объекту справа от оператора.  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект для проверки на равенство.|  
|`right`|Объект для проверки на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объекты равны, значение **false**, если объекты не равны.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает `left.category() == right.category() && left.value() == right.value()`.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  оператор!=  
 Проверяет неравенство объекта слева от оператора объекту справа от оператора.  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Объект для проверки на неравенство.|  
|`right`|Объект для проверки на неравенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объект, переданный в `left`, не равен объекту, переданному в `right`; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Функция возвращает `!(left == right)`.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  оператор&lt;  
 Проверяет, меньше ли какой-либо объект переданного для сравнения объекта.  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`left`|Сравниваемый объект.|  
|`right`|Сравниваемый объект.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объект, переданный в `left`, меньше, чем объект, переданный в `right`; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Эта функция проверяет порядок ошибок.  
  
## <a name="see-also"></a>См. также  
 [<system_error>](../standard-library/system-error.md)




