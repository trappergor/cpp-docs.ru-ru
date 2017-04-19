---
title: "Класс error_condition | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_condition class
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 4b9bc9b48c09c2b50b25eeb71a7fe9b5ad812157
ms.lasthandoff: 02/24/2017

---
# <a name="errorcondition-class"></a>Класс error_condition
Представляет коды ошибок, определенные пользователем.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>Примечания  
 Объект типа `error_condition` сохраняет значение кода ошибки и указатель на объект, представляющий [категорию](../standard-library/error-category-class.md) кодов ошибок, используемую для сообщаемых ошибках, определяемых пользователем.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[error_condition](#error_condition__error_condition)|Создает объект типа `error_condition`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#error_condition__value_type)|Тип, представляющий сохраненное значение кода ошибки.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[assign](#error_condition__assign)|Присваивает условию ошибки значение кода ошибки и категорию.|  
|[category](#error_condition__category)|Возвращает категорию ошибки.|  
|[clear](#error_condition__clear)|Очищает значение кода ошибки и категорию.|  
|[message](#error_condition__message)|Возвращает имя кода ошибки.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор==](#error_condition__operator_eq_eq)|Проверяет равенство между объектами `error_condition`.|  
|[оператор!=](#error_condition__operator_neq)|Проверяет неравенство между объектами `error_condition`.|  
|[оператор<](#error_condition__operator_lt_)|Проверяет, меньше ли объект `error_condition` переданного для сравнения объекта `error_code`.|  
|[оператор=](#error_condition__operator_eq)|Присваивает новое значение перечисления объекту `error_condition`.|  
|[operator bool](#error_condition__operator_bool)|Преобразует переменную типа `error_condition`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<system_error>  
  
 **Пространство имен:** std  
  
##  <a name="error_condition__assign"></a>  error_condition::assign  
 Присваивает условию ошибки значение кода ошибки и категорию.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`val`|Значение кода ошибки для хранения в `error_code`.|  
|`_Cat`|Категория ошибки для хранения в `error_code`.|  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет `val` как значение кода ошибки и указатель на `_Cat`.  
  
##  <a name="error_condition__category"></a>  error_condition::category  
 Возвращает категорию ошибки.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на сохраняемую категорию ошибки  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="error_condition__clear"></a>  error_condition::clear  
 Очищает значение кода ошибки и категорию.  
  
```
clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет нулевое значение кода ошибки и указатель на объект [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="error_condition__error_condition"></a>  error_condition::error_condition  
 Создает объект типа `error_condition`.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`val`|Значение кода ошибки для хранения в `error_condition`.|  
|`_Cat`|Категория ошибки для хранения в `error_condition`.|  
|`_Errcode`|Значение перечисления для хранения в `error_condition`.|  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор сохраняет нулевое значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Второй конструктор сохраняет `val` как значение кода ошибки и указатель на [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Третий конструктор сохраняет `(value_type)_Errcode` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="error_condition__message"></a>  error_condition::message  
 Возвращает имя кода ошибки.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `string`, представляющее имя кода ошибки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение `category().message(value())`.  
  
##  <a name="error_condition__operator_eq_eq"></a>  error_condition::operator==  
 Проверяет равенство между объектами `error_condition`.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Объект для проверки на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объекты равны, значение **false**, если объекты не равны.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `category() == right.category() && value == right.value()`.  
  
##  <a name="error_condition__operator_neq"></a>  error_condition::operator!=  
 Проверяет неравенство между объектами `error_condition`.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Объект для проверки на неравенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объект `error_condition` не равен объекту `error_condition`, передаваемому в `right`; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `!(*this == right)`.  
  
##  <a name="error_condition__operator_lt_"></a>  error_condition::operator&lt;  
 Проверяет, меньше ли объект `error_condition` переданного для сравнения объекта `error_code`.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Сравниваемый объект `error_condition`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true,** если объект `error_condition` меньше, чем объект `error_condition`, переданный для сравнения; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="error_condition__operator_eq"></a>  error_condition::operator=  
 Присваивает новое значение перечисления объекту `error_condition`.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Errcode`|Значение перечисления для присвоения объекту `error_condition`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект `error_condition`, которому функцией-членом присваивается новое значение перечисления.  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет `(value_type)error` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category). Он возвращает `*this`.  
  
##  <a name="error_condition__operator_bool"></a>  error_condition::operator bool  
 Преобразует переменную типа `error_condition`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение объекта `error_condition`.  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает значение, преобразуемое в `true`, только тогда, когда [значение](#error_condition__value) не равно нулю. Тип возвращаемого значения можно преобразовать только в `bool`, а не в `void *` или другие известные скалярные типы.  
  
##  <a name="error_condition__value"></a>  error_condition::value  
 Возвращает сохраненное значение кода ошибки.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сохраненное значение кода ошибки типа [value_type](#error_condition__value_type).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="error_condition__value_type"></a>  error_condition::value_type  
 Тип, представляющий сохраненное значение кода ошибки.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа — синоним для `int`.  
  
## <a name="see-also"></a>См. также  
 [Класс error_category](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




