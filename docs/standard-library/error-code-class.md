---
title: "Класс error_code | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- error_code
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_code class
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 82c70317383fe096c56b0d5b79bab24175d2872a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="errorcode-class"></a>Класс error_code
Представляет низкоуровневые системные ошибки, которые связаны с конкретной реализацией.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class error_code;
```  
  
## <a name="remarks"></a>Примечания  
 Объект типа `error_code` сохраняет значение кода ошибки и указатель на объект, представляющий [категорию](../standard-library/error-category-class.md) кодов ошибок, которые описывают сообщенные низкоуровневые системные ошибки.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[error_code](#error_code)|Создает объект типа `error_code`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#value_type)|Тип, представляющий сохраненное значение кода ошибки.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[assign](#assign)|Присваивает коду ошибки значение кода ошибки и категорию.|  
|[category](#category)|Возвращает категорию ошибки.|  
|[clear](#clear)|Очищает значение кода ошибки и категорию.|  
|[default_error_condition](#default_error_condition)|Возвращает условие ошибки по умолчанию.|  
|[message](#message)|Возвращает имя кода ошибки.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор==](#op_eq_eq)|Проверяет равенство между объектами `error_code`.|  
|[оператор!=](#op_neq)|Проверяет неравенство между объектами `error_code`.|  
|[оператор<](#op_lt)|Проверяет, меньше ли объект `error_code` переданного для сравнения объекта `error_code`.|  
|[оператор=](#op_eq)|Присваивает новое значение перечисления объекту `error_code`.|  
|[operator bool](#op_bool)|Преобразует переменную типа `error_code`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<system_error>  
  
 **Пространство имен:** std  
  
##  <a name="assign"></a>  error_code::assign  
 Присваивает коду ошибки значение кода ошибки и категорию.  
  
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
  
##  <a name="category"></a>  error_code::category  
 Возвращает категорию ошибки.  
  
```
const error_category& category() const;
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="clear"></a>  error_code::clear  
 Очищает значение кода ошибки и категорию.  
  
```
clear();
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет нулевое значение кода ошибки и указатель на объект [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="default_error_condition"></a>  error_code::default_error_condition  
 Возвращает условие ошибки по умолчанию.  
  
```
error_condition default_error_condition() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Условие [error_condition](../standard-library/error-condition-class.md), задаваемое условием [default_error_condition](../standard-library/error-category-class.md#default_error_condition).  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение `category().default_error_condition(value())`.  
  
##  <a name="error_code"></a>  error_code::error_code  
 Создает объект типа `error_code`.  
  
```
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`val`|Значение кода ошибки для хранения в `error_code`.|  
|`_Cat`|Категория ошибки для хранения в `error_code`.|  
|`_Errcode`|Значение перечисления для хранения в `error_code`.|  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор сохраняет нулевое значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Второй конструктор сохраняет `val` как значение кода ошибки и указатель на [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Третий конструктор сохраняет `(value_type)_Errcode` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="message"></a>  error_code::message  
 Возвращает имя кода ошибки.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `string`, представляющее имя кода ошибки.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение `category().message(value())`.  
  
##  <a name="op_eq_eq"></a>  error_code::operator==  
 Проверяет равенство между объектами `error_code`.  
  
```
bool operator==(const error_code& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Объект для проверки на равенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объекты равны, значение **false**, если объекты не равны.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `category() == right.category() && value == right.value()`.  
  
##  <a name="op_neq"></a>  error_code::operator!=  
 Проверяет неравенство между объектами `error_code`.  
  
```
bool operator!=(const error_code& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Объект для проверки на неравенство.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true**, если объект `error_code` не равен объекту `error_code`, передаваемому в `right`; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `!(*this == right)`.  
  
##  <a name="op_lt"></a>  error_code::operator&lt;  
 Проверяет, меньше ли объект [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) переданного для сравнения объекта `error_code`.  
  
```
bool operator<(const error_code& right) const;
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`right`|Объект error_code для сравнения.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение **true,** если объект `error_code` меньше, чем объект `error_code`, переданный для сравнения; в противном случае — значение **false**.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член возвращает `category() < right.category() || category() == right.category() && value < right.value()`.  
  
##  <a name="op_eq"></a>  error_code::operator=  
 Присваивает новое значение перечисления объекту [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31).  
  
```
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type&
 operator=(_Enum _Errcode);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`_Errcode`|Значение перечисления для присвоения объекту `error_code`.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект `error_code`, которому функцией-членом присваивается новое значение перечисления.  
  
### <a name="remarks"></a>Примечания  
 Функция-член сохраняет `(value_type)_Errcode` как значение кода ошибки и указатель на [generic_category](../standard-library/system-error-functions.md#generic_category). Он возвращает `*this`.  
  
##  <a name="op_bool"></a>  error_code::operator bool  
 Преобразует переменную типа `error_code`.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение объекта `error_code`.  
  
### <a name="remarks"></a>Примечания  
 Оператор возвращает значение, преобразуемое в `true`, только тогда, когда [значение](#value) не равно нулю. Тип возвращаемого значения можно преобразовать только в `bool`, а не в `void *` или другие известные скалярные типы.  
  
##  <a name="value"></a>  error_code::value  
 Возвращает сохраненное значение кода ошибки.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Сохраненное значение кода ошибки типа [value_type](#value_type).  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="value_type"></a>  error_code::value_type  
 Тип, представляющий сохраненное значение кода ошибки.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа — синоним для `int`.  
  
## <a name="see-also"></a>См. также  
 [Класс error_category](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




