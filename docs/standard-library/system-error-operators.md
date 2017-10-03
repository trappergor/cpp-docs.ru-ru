---
title: "Операторы &lt;system_error&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ed01a5abeb54f5071968555b563849e2cd4ac1af
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="ltsystemerrorgt-operators"></a>Операторы &lt;system_error&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[оператор&lt;](#op_lt)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  оператор==  
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
  
##  <a name="op_neq"></a>  оператор!=  
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
  
##  <a name="op_lt"></a>  оператор&lt;  
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




