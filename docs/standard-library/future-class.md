---
title: Класс future | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 77b3c96d2c579b9fa3081ad7223ac254a727a88b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956642"
---
# <a name="future-class"></a>Класс future

Описывает *асинхронный возвращаемый объект*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>Примечания

Каждый стандартный *асинхронный поставщик* возвращает объект, тип которого является экземпляром данного шаблона. Объект `future` предоставляет только доступ к асинхронному поставщику, связанному с ним. Если требуется несколько асинхронных возвращаемых объектов, связанных с одним асинхронным поставщиком, скопируйте объект `future` в объект [shared_future](../standard-library/shared-future-class.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[future](#future)|Создает объект `future`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[get](#get)|Получает результат, который хранится в связанном асинхронном состоянии.|
|[Предоставить общий доступ](#share)|Преобразует объект в `shared_future`.|
|[допустимый](#valid)|Указывает, является ли объект не пустым.|
|[wait](#wait)|Блокирует текущий поток, пока не будет готово связанное асинхронное состояние.|
|[wait_for](#wait_for)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не истечет указанный период времени.|
|[wait_until](#wait_until)|Выполняет блокировку, пока не будет готово связанное асинхронное состояние или не наступит указанный момент времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[future::operator=](#op_eq)|Передает связанное асинхронное состояние из указанного объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<будущих >

**Пространство имен:** std

## <a name="future"></a>  Конструктор future::future

Создает объект `future`.

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Другие* A `future` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект `future`, который не имеет связанного асинхронного состояния.

Второй конструктор создает `future` и передает связанное асинхронное состояние из *других*. *Другие* больше не имеет связанного асинхронного состояния.

## <a name="get"></a>  future::get

Получает результат, который хранится в связанном асинхронном состоянии.

```cpp
Ty get();
```

### <a name="return-value"></a>Возвращаемое значение

Если результат — исключение, метод создает его повторно. В противном случае результат будет возвращен.

### <a name="remarks"></a>Примечания

До получения результата данный метод блокирует текущий поток, пока не будет готово связанное асинхронное состояние.

Для частичной специализации `future<Ty&>` хранимое значение является ссылкой на объект, который был передан асинхронному поставщику как возвращаемое значение.

Так как сохраненные значения не существуют для специализации `future<void>`, метод возвращает **void**.

В других специализациях метод перемещает свое возвращаемое значение из сохраненного значения. Таким образом, этот метод следует вызывать только один раз.

## <a name="op_eq"></a>  future::operator=

Передает связанное асинхронное состояние из указанного объекта.

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Справа* A `future` объекта.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

После передачи *справа* больше не имеет связанного асинхронного состояния.

## <a name="share"></a>  future::share

Преобразует объект в объект [shared_future](../standard-library/shared-future-class.md).

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>Возвращаемое значение

`shared_future(move(*this))`

## <a name="valid"></a>  future::valid

Указывает, имеет ли объект связанное асинхронное состояние.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект имеет связанное асинхронное состояние; в противном случае **false**.

## <a name="wait"></a>  future::wait

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready*.

```cpp
void wait() const;
```

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение *ready*, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="wait_for"></a>  future::wait_for

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не истечет указанный период времени.

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Параметры

*Rel_time* объект [chrono::duration](../standard-library/duration-class.md) , указывающий максимальный интервал времени, поток блокируется.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение "ready", только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="wait_until"></a>  future::wait_until

Блокирует текущий поток, пока связанное асинхронное состояние не получит значение *ready* или не наступит указанный момент времени.

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Параметры

*Abs_time* объект [chrono::time_point](../standard-library/time-point-class.md) объект, который указывает время, после чего поток можно разблокировать.

### <a name="return-value"></a>Возвращаемое значение

Состояние [future_status](../standard-library/future-enums.md#future_status), которое указывает причину возврата.

### <a name="remarks"></a>Примечания

Связанное асинхронное состояние имеет значение *ready*, только если его асинхронный поставщик сохранил возвращаемое значение или исключение.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
