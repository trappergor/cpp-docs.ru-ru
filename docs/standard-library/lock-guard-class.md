---
title: Класс lock_guard | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f53732fee62906da19a5771c8598cce51fc6331
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953762"
---
# <a name="lockguard-class"></a>Класс lock_guard

Представляет шаблон, для которого можно создать экземпляры и объект, деструктор которого разблокирует `mutex`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Примечания

В аргументе шаблона `Mutex` должно быть указано имя *типа мьютекс*.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`lock_guard::mutex_type`|Синоним для аргумента шаблона `Mutex`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[lock_guard](#lock_guard)|Создает объект `lock_guard`.|
|[Деструктор lock_guard::~lock_guard](#dtorlock_guard_destructor)|Снимает блокировку `mutex`, переданного в конструктор.|

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex >

**Пространство имен:** std

## <a name="lock_guard"></a>  Конструктор lock_guard::lock_guard

Создает объект `lock_guard`.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Параметры

*Mtx* объект *тип мьютекса* объекта.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект типа `lock_guard` и блокировки *Mtx*. Если *Mtx* не является рекурсивным мьютексом, его необходимо разблокировать при вызове этого конструктора.

Второй конструктор не блокирует *Mtx*. *Mtx* должен быть заблокирован при вызове этого конструктора. Конструктор не выдает никаких исключений.

## <a name="dtorlock_guard_destructor"></a>  Деструктор lock_guard::~lock_guard

Снимает блокировку `mutex`, переданного в конструктор.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Примечания

Если `mutex` не существует при выполнении деструктора, поведение не определено.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
