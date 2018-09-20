---
title: Класс SafeInt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb264447aff789e375afeb9f0db26d2205b3eb2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374487"
---
# <a name="safeint-class"></a>Класс SafeInt

Расширяет примитивам целое число, чтобы помочь в предотвращении переполнения для целочисленного значения и позволяет сравнивать разные типы целых чисел.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>
class SafeInt;
```

### <a name="parameters"></a>Параметры

|Шаблон|Описание|
|--------------|-----------------|
|T|Тип целого числа или логический параметр, **SafeInt** заменяет.|
|E|Тип перечислимых данных, который определяет политику обработки ошибок.|
|U|Тип целого числа или логического параметра для дополнительного операнда.|

|Параметр|Описание|
|---------------|-----------------|
|*правая часть*|[in] Входной параметр, представляющий значение правой стороны оператора в несколько отдельные функции.|
|*i*|[in] Входной параметр, представляющий значение правой стороны оператора в несколько отдельные функции.|
|*BITS*|[in] Входной параметр, представляющий значение правой стороны оператора в несколько отдельные функции.|

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Конструктор по умолчанию.|

### <a name="assignment-operators"></a>Операторы присваивания

|name|Синтаксис|
|----------|------------|
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|
|=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|
|=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|
|=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|

### <a name="casting-operators"></a>Операторы приведения

|name|Синтаксис|
|----------|------------|
|bool|`operator bool() throw()`|
|char|`operator char() const`|
|signed char|`operator signed char() const`|
|unsigned char|`operator unsigned char() const`|
|__int16|`operator __int16() const`|
|unsigned __int16|`operator unsigned __int16() const`|
|__int32|`operator __int32() const`|
|unsigned __int32|`operator unsigned __int32() const`|
|long|`operator long() const`|
|unsigned long|`operator unsigned long() const`|
|__int64|`operator __int64() const`|
|unsigned __int64|`operator unsigned __int64() const`|
|wchar_t|`operator wchar_t() const`|

### <a name="comparison-operators"></a>Операторы сравнения

|name|Синтаксис|
|----------|------------|
|<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|
|<|`bool operator< (SafeInt<T,E> rhs) const throw()`|
|>=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|
|>=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|
|>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|
|>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|
|<=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|
|<=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|
|==|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|
|==|`bool operator== (bool rhs) const throw()`|
|==|`bool operator== (SafeInt<T,E> rhs) const throw()`|
|!=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|
|!=|`bool operator!= (bool b) const throw()`|
|!=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|

### <a name="arithmetic-operators"></a>Арифметические операторы

|name|Синтаксис|
|----------|------------|
|+|`const SafeInt<T,E>& operator+ () const throw()`|
|-|`SafeInt<T,E> operator- () const`|
|++|`SafeInt<T,E>& operator++ ()`|
|--|`SafeInt<T,E>& operator-- ()`|
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|
|%=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|
|*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|
|*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|
|*=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|
|*=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|
|/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|
|/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|
|/=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|
|/=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|
|+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|
|+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|
|+=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|
|+=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|
|-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|
|-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|
|-=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|
|-=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|

### <a name="logical-operators"></a>Логические операторы

|name|Синтаксис|
|----------|------------|
|!|`bool operator !() const throw()`|
|~|`SafeInt<T,E> operator~ () const throw()`|
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|
|<<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|
|<<=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|
|>>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|
|>>=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|
|&=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|
|&=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|
|^=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|
|^=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|
|&#124;=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|
|&#124;=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|

## <a name="remarks"></a>Примечания

**SafeInt** класс обеспечивает защиту от переполнения для целочисленного значения в математических операций. Например, рассмотрите возможность добавления двух 8-битовых целых чисел: одна имеет значение 200, а второй имеет значение 100. Правильный математической операции будет 200 + 100 = 300. Тем не менее из-за предел 8-разрядное целое число, верхняя разрядное будут потеряны, и компилятор возвращает 44 (300-2<sup>8</sup>) в результате. Любая операция, которая зависит от математические уравнения создаст непредвиденное поведение.

**SafeInt** класс проверяет, происходит ли арифметическое переполнение или ли в коде предпринимается попытка деления на ноль. В обоих случаях класс вызывает обработчик ошибок для предупреждения программа потенциальные проблемы.

Этот класс также позволяет сравнить два различных типа целых чисел, как они станут **SafeInt** объектов. Как правило при выполнении сравнения, необходимо сначала преобразовать числа, которые нужно иметь тот же тип. Приведение одного числа на другой тип часто требует проверки, чтобы убедиться в том, что не происходит потери данных.

В таблице операторы в этом разделе перечислены математические операторы и операторы сравнения поддерживаемых **SafeInt** класса. Наиболее математические операторы возвращают **SafeInt** объект типа `T`.

Операции сравнения между **SafeInt** и целочисленный тип данных, которые могут выполняться в любом направлении. Например, оба `SafeInt<int>(x) < y` и `y> SafeInt<int>(x)` являются допустимыми и вернет тот же результат.

Многие бинарные операторы не поддерживают с двумя разными **SafeInt** типов. Примером этого является `&` оператор. `SafeInt<T, E> & int` поддерживается, но `SafeInt<T, E> & SafeInt<U, E>` не является. В последнем примере компилятор не знает, какой тип возвращаемого параметра. Одним из решений этой проблемы состоит в приведении второй параметр в базовый тип. Используя те же параметры, это можно сделать с помощью `SafeInt<T, E> & (U)SafeInt<U, E>`.

> [!NOTE]
> Для любой битовых операций: два различных параметра должен быть тот же размер. Если отличаются размеры, компилятор выдаст [ASSERT](../mfc/reference/diagnostic-services.md#assert) исключение. Результаты этой операции невозможно гарантировать точность. Чтобы устранить эту проблему, приведения параметра меньшего размера, пока он не совпадает с размером больше параметра.

Для операторов сдвига сдвиг больше бит не существует для типа шаблона приведет к возникновению исключения ASSERT. Это не будет действовать в режиме выпуска. Смешивание два типа параметров SafeInt возможен для операторов сдвига, так как тип возвращаемого значения совпадает со значением исходного типа. Число справа от оператора лишь указывает количество битов для сдвига.

При выполнении логическое сравнение с объектом SafeInt, строго арифметические сравнения. Например рассмотрим эти выражения:

- `SafeInt<uint>((uint)~0) > -1`

- `((uint)~0) > -1`

Первая инструкция разрешается в **true**, но разрешается во второй инструкции **false**. Поразрядное отрицание 0 — 0xFFFFFFFF. Во втором операторе оператор сравнения по умолчанию сравнивает 0xFFFFFFFF для 0xFFFFFFFF и рассматривает их как равные. Оператор сравнения для **SafeInt** класс осознает, что второй параметр является отрицательным, тогда как первый параметр — без знака. Таким образом, несмотря на то, что битовое представление идентичен, **SafeInt** логический оператор осознает, что целое число без знака больше, чем значение -1.

Будьте внимательны при использовании **SafeInt** класса вместе с `?:` троичный оператор. Рассмотрим следующую строку кода.

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : -1;
```

Компилятор преобразует его в это:

```cpp
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);
```

Если `flag` — **false**, компилятор создает исключение вместо присвоения значения от -1 до `x`. Таким образом Чтобы избежать этого, правильный код для использования является следующую строку.

```cpp
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;
```

`T` и `U` можно назначить логический тип, тип символа или целочисленный тип. Целое число, подписанные или неподписанные типов и любого размера, от 8-битных до 64 бит.

> [!NOTE]
> Несмотря на то что **SafeInt** класса принимает любого типа целого числа, он выполняет более эффективно с неподписанными типами.

`E` — Это механизм обработки ошибок, **SafeInt** использует. Библиотека SafeInt входят два механизма обработки ошибок. Политика по умолчанию — `SafeIntErrorPolicy_SafeIntException`, какие вызывает [класс SafeIntException](../windows/safeintexception-class.md) исключения при возникновении ошибки. Другой политикой является `SafeIntErrorPolicy_InvalidParameter`, который останавливает программу, если произошла ошибка.

Существует два способа настройки политики ошибок. Первый вариант — установить параметр `E` при создании **SafeInt**. Используйте этот параметр, если вы хотите изменить политику обработки одной ошибок **SafeInt**. Другой вариант — для определения _SAFEINT_DEFAULT_ERROR_POLICY быть настраиваемый класс обработки ошибок, перед включением **SafeInt** библиотеки. Используйте этот параметр, если вы хотите изменить политику для всех экземпляров обработки ошибок по умолчанию **SafeInt** класса в коде.

> [!NOTE]
> Настраиваемый класс, который обрабатывает ошибки библиотека SafeInt не должна возвращать управление коду, который вызывается обработчик ошибок. После вызова обработчика ошибок, результат **SafeInt** операция не может быть доверенным.

## <a name="requirements"></a>Требования

**Заголовок:** safeint.h

**Пространство имен:** msl::utilities

## <a name="see-also"></a>См. также

[Библиотека SafeInt](../windows/safeint-library.md)<br/>
[Класс SafeIntException](../windows/safeintexception-class.md)