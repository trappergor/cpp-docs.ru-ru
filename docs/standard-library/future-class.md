---
title: "Класс future | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6de4fecd3f5f65ac48cbb49f2ed4f874f4283487
ms.lasthandoff: 02/24/2017

---
# <a name="future-class"></a>Класс future
Описывает *асинхронный возвращаемый объект*.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
class future;
```  
  
## <a name="remarks"></a>Примечания  
 Каждый стандартный *асинхронный поставщик* возвращает объект, тип которого является экземпляром данного шаблона. Объект `future` предоставляет только доступ к асинхронному поставщику, связанному с ним. Если требуется несколько асинхронных возвращаемых объектов, связанных с одним асинхронным поставщиком, скопируйте объект `future` в объект [shared_future](../standard-library/shared-future-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор future::future](#future__future_constructor)|Создает объект `future`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[future::get](#future__get_method)|Получает результат, который хранится в связанном асинхронном состоянии.|  
|[future::share](#future__share_method)|Преобразует объект в `shared_future`.|  
|[future::valid](#future__valid_method)|Указывает, является ли объект не пустым.|  
|[future::wait](#future__wait_method)|Блокирует текущий поток, пока не будет готово связанное асинхронное состояние.|  
|[future::wait_for](#future__wait_for_method)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не истечет указанный период времени.|  
|[future::wait_until](#future__wait_until_method)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не наступит указанный момент времени.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[future::operator=](#future__operator_eq)|Передает связанное асинхронное состояние из указанного объекта.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
##  <a name="a-namefuturefutureconstructora--futurefuture-constructor"></a><a name="future__future_constructor"></a>  Конструктор future::future  
 Создает объект `future`.  
  
```
future() noexcept;
future(future&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `future`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект `future`, который не имеет связанного асинхронного состояния.  
  
 Второй конструктор создает объект `future` и передает связанное асинхронное состояние из `Other`. `Other` больше не имеет связанного асинхронного состояния.  
  
##  <a name="a-namefuturegetmethoda--futureget"></a><a name="future__get_method"></a>  future::get  
 Получает результат, который хранится в связанном асинхронном состоянии.  
  
```
Ty get();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если результат — исключение, метод создает его повторно. В противном случае результат будет возвращен.  
  
### <a name="remarks"></a>Примечания  
 До получения результата данный метод блокирует текущий поток, пока не будет готово связанное асинхронное состояние.  
  
 Для частичной специализации `future<Ty&>` хранимое значение является ссылкой на объект, который был передан асинхронному поставщику как возвращаемое значение.  
  
 Так как для специализации `future<void>` хранимые значения не существуют, метод возвращает `void`.  
  
 В других специализациях метод перемещает свое возвращаемое значение из сохраненного значения. Таким образом, этот метод следует вызывать только один раз.  
  
##  <a name="a-namefutureoperatoreqa--futureoperator"></a><a name="future__operator_eq"></a>  future::operator=  
 Передает связанное асинхронное состояние из указанного объекта.  
  
```
future& operator=(future&& Right) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Объект `future`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 После передачи `Right` больше не имеет связанного асинхронного состояния.  
  
##  <a name="a-namefuturesharemethoda--futureshare"></a><a name="future__share_method"></a>  future::share  
 Преобразует объект в объект [shared_future](../standard-library/shared-future-class.md).  
  
```
shared_future<Ty> share();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `shared_future(move(*this))`  
  
##  <a name="a-namefuturevalidmethoda--futurevalid"></a><a name="future__valid_method"></a>  future::valid  
 Указывает, имеет ли объект связанное асинхронное состояние.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объект имеет связанное асинхронное состояние; в противном случае — значение `false`.  
  
##  <a name="a-namefuturewaitmethoda--futurewait"></a><a name="future__wait_method"></a>  future::wait  
 Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready*.  
  
```cpp  
void wait() const;
```  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение *ready*, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
##  <a name="a-namefuturewaitformethoda--futurewaitfor"></a><a name="future__wait_for_method"></a>  future::wait_for  
 Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не истечет указанный период времени.  
  
```
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Параметры  
 `Rel_time`  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает на максимальный интервал времени, в течение которого поток может быть заблокирован.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние [future_status](../standard-library/future-enums.md#future_status_enumeration), которое указывает причину возврата.  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение "ready", только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
##  <a name="a-namefuturewaituntilmethoda--futurewaituntil"></a><a name="future__wait_until_method"></a>  future::wait_until  
 Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не наступит указанный момент времени.  
  
```cpp  
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Параметры  
 `Abs_time`  
 Объект [chrono::time_point](../standard-library/time-point-class.md), который указывает время, по истечении которого поток можно разблокировать.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Состояние [future_status](../standard-library/future-enums.md#future_status_enumeration), которое указывает причину возврата.  
  
### <a name="remarks"></a>Примечания  
 Связанное асинхронное состояние имеет значение *ready*, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




