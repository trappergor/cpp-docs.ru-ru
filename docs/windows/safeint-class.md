---
title: "Класс SafeInt | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: SafeInt
dev_langs: C++
helpviewer_keywords: SafeInt class
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea076ea092257fd5bf6acd6d597f79ef42dd96f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="safeint-class"></a>Класс SafeInt
Расширяет примитивы целое число со знаком для предотвращения переполнения для целочисленных значений и позволяет сравнить различные виды целых чисел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Шаблон|Описание:|  
|--------------|-----------------|  
|T|Тип целого числа или логического параметра, `SafeInt` заменяет.|  
|E|Тип данных перечисления, который определяет политику обработки ошибок.|  
|U|Тип целого числа или логического параметра для дополнительного операнда.|  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|[in] rhs|Входной параметр, представляющий значение справа от оператора в несколько автономного функций.|  
|[in] i|Входной параметр, представляющий значение справа от оператора в несколько автономного функций.|  
|[in] bits|Входной параметр, представляющий значение справа от оператора в несколько автономного функций.|  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
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
 `SafeInt` Класс предотвращает переполнение целочисленного значения в математических операциях. Например, рассмотрите возможность добавления двух 8-битовых целых чисел: одна имеет значение 200, а второй имеет значение 100. Правильный математической операции будет 200 + 100 = 300. Однако из-за предел 8-разрядное целое число, будут потеряны верхний бит и компилятор возвращает 44 (300-2<sup>8</sup>) в результате. Любая операция, которая зависит от математических уравнения создаст непредвиденное поведение.  
  
 `SafeInt` Класс проверяет, выполняется ли арифметическое переполнение или ли в коде предпринимается попытка деления на ноль. В обоих случаях класс вызывает обработчик ошибок, чтобы предупредить программа потенциальные проблемы.  
  
 Этот класс также позволяет сравнить два различных типа целых чисел, при условии, что они являются `SafeInt` объектов. Как правило при выполнении сравнения, необходимо сначала преобразовать чисел, чтобы быть того же типа. Приведение одно число другого типа часто требует проверки, чтобы убедиться в том, что не происходит потери данных.  
  
 В таблице операторы в этом разделе перечислены математические операторы и операторы сравнения поддерживаемые `SafeInt` класса. Наиболее математические операторы возвращают `SafeInt` объекта типа `T`.  
  
 Операции сравнения между `SafeInt` и целочисленный тип, которые могут выполняться в любом направлении. Например, оба `SafeInt<int>(x) < y` и `y > SafeInt<int>(x)` являются допустимыми и будет возвращать тот же результат.  
  
 Многие бинарные операторы не поддерживают с двумя разными `SafeInt` типов. Примером этого является `&` оператор. `SafeInt<T, E> & int`поддерживается, но `SafeInt<T, E> & SafeInt<U, E>` не является. В последнем примере компилятор не знает, какой тип возвращаемого параметра. Одно из решений этой проблемы состоит в приведении второй параметр обратно к базовому типу. Используя те же параметры, это можно сделать с помощью `SafeInt<T, E> & (U)SafeInt<U, E>`.  
  
> [!NOTE]
>  Для любого побитовых операций двух различных параметров должно быть одинакового размера. Если отличаются размеры, компилятор выдаст [ASSERT](../mfc/reference/diagnostic-services.md#assert) исключение. Результаты этой операции не гарантируется точным. Чтобы устранить эту проблему, приведения параметра меньшего размера, пока он не совпадает с размером больше параметра.  
  
 Для операторов сдвига сдвиг битов больше не существует для типа шаблона вызовет исключение ASSERT. Это не будет действовать в режиме выпуска. Смешивание два типа параметров SafeInt возможна для операторов сдвига, так как тип возвращаемого значения совпадает с исходным типом. Число с правой стороны оператора лишь указывает число разрядов для поворота.  
  
 При выполнении логическое сравнение с объектом SafeInt строго арифметического сравнения. Например рассмотрим следующие выражения:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 Первая инструкция разрешается в `true`, но разрешается во второй инструкции `false`. Поразрядное отрицание 0 — 0xFFFFFFFF. Во второй инструкции оператор сравнения по умолчанию сравнивает 0xFFFFFFFF до 0xFFFFFFFF и рассматривает их как равные. Оператор сравнения для `SafeInt` класс выясняет, что второй параметр является отрицательным, тогда как первый параметр является число без знака. Таким образом, несмотря на то, что битовое представление идентичен `SafeInt` логический оператор выясняет, что целое число без знака больше, чем значение -1.  
  
 Следует соблюдать осторожность при использовании `SafeInt` класса вместе с `?:` троичный оператор. Рассмотрим следующую строку кода.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Компилятор преобразует его в это:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Если `flag` — `false`, компилятор выдает исключение вместо присваивания значения от -1 до `x`. Таким образом Чтобы избежать подобного поведения, правильный код для использования является следующая строка.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T`и `U` могут назначаться логического типа, тип символа или целочисленный тип. Целое число со знаком, подписанные или неподписанные типов и любых размеров из 8 бит до 64 бит.  
  
> [!NOTE]
>  Несмотря на то что `SafeInt` класса принимает любого типа целого числа со знаком, он выполняет более эффективно с типов без знака.  
  
 `E`является механизмом обработки ошибок, `SafeInt` использует. Библиотека SafeInt входят два механизмы обработки ошибок. Политика по умолчанию — `SafeIntErrorPolicy_SafeIntException`, какие вызывает [класс SafeIntException](../windows/safeintexception-class.md) исключение при возникновении ошибки. Другая политика является `SafeIntErrorPolicy_InvalidParameter`, который останавливает программу, если возникает ошибка.  
  
 Существует два варианта для настройки политики ошибки. Первый параметр — для настройки параметра `E` при создании `SafeInt`. Используйте этот параметр, если вы хотите изменить обработку политики только для одного ошибок `SafeInt`. Другим вариантом является определение `_SAFEINT_DEFAULT_ERROR_POLICY` в настраиваемый класс обработки ошибок, чтобы включить `SafeInt` библиотеки. Используйте этот параметр, если вы хотите изменить политику для всех экземпляров обработки ошибок по умолчанию `SafeInt` классу в коде.  
  
> [!NOTE]
>  Настраиваемый класс, который обрабатывает ошибки библиотека SafeInt не должна возвращать управление коду, который вызывается обработчик ошибок. После вызова обработчика ошибок, результат `SafeInt` операция не может быть доверенным.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeIntException](../windows/safeintexception-class.md)