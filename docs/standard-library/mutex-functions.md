---
title: Функции и переменные &lt;мьютексов&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: 85ed95250b5563cd8a7c1ef9cfc0ee048cb3bc60
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858216"
---
# <a name="ltmutexgt-functions-and-variables"></a>Функции и переменные &lt;мьютексов&gt;

||||
|-|-|-|
|[adopt_lock](#adopt_lock)|[call_once](#call_once)|[defer_lock](#defer_lock)|
|[lock](#lock)|[try_to_lock](#try_to_lock)|

## <a name="adopt_lock"></a>  Переменная adopt_lock

Представляет объект, который можно передать в конструкторы для [lock_guard](../standard-library/lock-guard-class.md) и [unique_lock](../standard-library/unique-lock-class.md), чтобы указать на блокировку объекта мьютекса, также передаваемого в конструктор.

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a>  call_once

Предоставляет механизм для однократного вызова указанного объекта во время выполнения.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>Параметры

`Flag` Объект [once_flag](../standard-library/once-flag-structure.md) объект, который гарантирует, что вызываемый объект вызывается только один раз.

`F` Вызываемый объект.

`A` Список аргументов.

### <a name="remarks"></a>Примечания

Если `Flag` является недопустимым, функция выдает [system_error](../standard-library/system-error-class.md) с кодом ошибки `invalid_argument`. В противном случае функция-шаблон использует свой аргумент `Flag`, чтобы убедиться, что она вызывает `F(A...)` успешно ровно один раз, независимо от количества вызовов функции-шаблона. Если `F(A...)` завершает работу, создавая исключение, вызов считается неуспешным.

## <a name="defer_lock"></a>  Переменная defer_lock

Представляет объект, который может быть передан в конструктор для [unique_lock](../standard-library/unique-lock-class.md). Это означает, что конструктор не должен блокировать объект мьютекса, который также ему передается.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a>  lock

Пытается заблокировать все аргументы без взаимоблокировки.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Примечания

Аргументы функции-шаблона должны быть типа *мьютекс*, за исключением того, что при вызове `try_lock` могут вызываться исключения.

Функция блокирует все свои аргументы без взаимоблокировки путем вызовов `lock`, `try_lock`, и `unlock`. Если вызов `lock` или `try_lock` приводит к исключению, функция вызывает `unlock` для любых объектов-мьютексов, которые были успешно заблокированы до повторного создания исключения.

## <a name="try_to_lock"></a>  Переменная try_to_lock

Представляет объект, который можно передать в конструктор для [unique_lock](../standard-library/unique-lock-class.md), чтобы указать, что конструктор должен попытаться разблокировать объект `mutex`, который также передается в него, без блокировки.

```cpp
const try_to_lock_t try_to_lock;
```

## <a name="see-also"></a>См. также

[\<mutex>](../standard-library/mutex.md)<br/>
