---
title: "Класс shared_future | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
dev_langs:
- C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
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
ms.openlocfilehash: 84b55dc763d4cd254e4aca55c01690ce5abf0152
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="sharedfuture-class"></a>Класс shared_future
Описывает *асинхронный возвращаемый объект*. В отличие от объекта [future](../standard-library/future-class.md), *асинхронный поставщик* может быть связан с любым числом объектов `shared_future`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
class shared_future;
```  
  
## <a name="remarks"></a>Примечания  
 Не вызывайте никакие методы, кроме `valid`, `operator=`, и деструктор в объекте `shared_future`, который является *пустым*.  
  
 Объекты `shared_future` не синхронизируются. Вызов методов из нескольких потоков для одного объекта становится причиной состязания за данные с непредсказуемыми результатами.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[shared_future](#shared_future)|Создает объект `shared_future`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get](#get)|Получает результат, который хранится в *связанном асинхронном состоянии*.|  
|[Допустимые](#valid)|Указывает, является ли объект не пустым.|  
|[Ожидание](#wait)|Блокирует текущий поток, пока не будет готово связанное асинхронное состояние.|  
|[wait_for](#wait_for)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не истечет указанный период времени.|  
|[wait_until](#wait_until)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не наступит указанный момент времени.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[shared_future::operator=](#op_eq)|Назначает новое связанное асинхронное состояние.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<будущих >  
  
 **Пространство имен:** std  
  
##  <a name="get"></a>shared_future::Get
 Получает результат, который хранится в *связанном асинхронном состоянии*.  
  
```
const Ty& get() const;

Ty& get() const;

void get() const;
```  
  
### <a name="remarks"></a>Примечания  
 Если результат — исключение, метод создает его повторно. В противном случае результат будет возвращен.  
  
 До получения результата данный метод блокирует текущий поток, пока не будет готово связанное асинхронное состояние.  
  
 Для частичной специализации `shared_future<Ty&>` хранимое значение является ссылкой на объект, который был передан *асинхронному поставщику* как возвращаемое значение.  
  
 Так как для специализации `shared_future<void>` хранимые значения не существуют, метод возвращает `void`.  
  
##  <a name="op_eq"></a>  shared_future::operator=  
 Передает *связанное асинхронное состояние* из указанного объекта.  
  
```
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Объект `shared_future`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 Для первого оператора `Right` больше не имеет связанного асинхронного состояния.  
  
 Для второго метода `Right` поддерживает его связанное асинхронное состояние.  
  
##  <a name="shared_future"></a> Конструктор shared_future::shared_future  
 Создает объект `shared_future`.  
  
```
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Класс [future](../standard-library/future-class.md) или объект `shared_future`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект `shared_future`, который не имеет *связанного асинхронного состояния*.  
  
 Второй и третий конструкторы создают объект `shared_future` и передают связанное асинхронное состояние из `Right`. `Right` больше не имеет связанного асинхронного состояния.  
  
 Четвертый конструктор создает объект `shared_future`, который имеет то же связанное асинхронное состояние, что и `Right`.  
  
##  <a name="valid"></a>shared_future::Valid
 Указывает, имеет ли объект *связанное асинхронное состояние*.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объект имеет связанное асинхронное состояние; в противном случае — значение `false`.  
  
##  <a name="wait"></a>shared_future::wait
 Блокирует текущий поток, пока *связанное асинхронное состояние* не будет иметь значение *ready*.  
  
```
void wait() const;
```  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение ready, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
##  <a name="wait_for"></a>shared_future::wait_for
 Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не истечет указанный период времени.  
  
```
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Параметры  
 `Rel_time`  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает на максимальный интервал времени, в течение которого поток может быть заблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение *ready*, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
##  <a name="wait_until"></a>shared_future::wait_until
 Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не наступит указанный момент времени.  
  
```
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Параметры  
 `Abs_time`  
 Объект [chrono::time_point](../standard-library/time-point-class.md), который указывает время, по истечении которого поток можно разблокировать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение ready, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




