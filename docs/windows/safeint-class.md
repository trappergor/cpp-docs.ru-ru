---
title: "Класс SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt - класс"
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 16
---
# Класс SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Расширяет примитивов целые числа, чтобы предотвратить переполнение целые числа и позволяет сравнивать различные типы целых чисел.  
  
## Синтаксис  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### Параметры  
  
|Шаблон|Описание|  
|------------|--------------|  
|T|Тип целого числа или логического параметра, `SafeInt` заменяет.|  
|E|Тип перечислимых данных, задающим политику обработки ошибок.|  
|U|Тип целого числа или логического параметра для вторичного операнда.|  
  
|Параметр|Описание|  
|--------------|--------------|  
|\[in\] rhs|Входной параметр, представляющий значение в правой части оператора в нескольких изолированных функций.|  
|\[in\] I|Входной параметр, представляющий значение в правой части оператора в нескольких изолированных функций.|  
|\[in\] биты|Входной параметр, представляющий значение в правой части оператора в нескольких изолированных функций.|  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Конструктор по умолчанию.|  
  
### Операторы присваивания  
  
|Name|Синтаксис|  
|----------|---------------|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### Операторы приведения  
  
|Name|Синтаксис|  
|----------|---------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|\_\_int16|`operator __int16() const`|  
|unsigned \_\_int16|`operator unsigned __int16() const`|  
|\_\_int32|`operator __int32() const`|  
|unsigned \_\_int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|\_\_int64|`operator __int64() const`|  
|unsigned \_\_int64|`operator unsigned __int64() const`|  
|wchar\_t|`operator wchar_t() const`|  
  
### Операторы сравнения  
  
|Name|Синтаксис|  
|----------|---------------|  
|\<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|\<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|\>\=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|\>\=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|\>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|\>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|\<\=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|\<\=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|\=\=|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|\=\=|`bool operator== (bool rhs) const throw()`|  
|\=\=|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|\!\=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|\!\=|`bool operator!= (bool b) const throw()`|  
|\!\=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### Арифметические операторы  
  
|Name|Синтаксис|  
|----------|---------------|  
|\+|`const SafeInt<T,E>& operator+ () const throw()`|  
|\-|`SafeInt<T,E> operator- () const`|  
|\+\+|`SafeInt<T,E>& operator++ ()`|  
|\-\-|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|\*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|\*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|\*\=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|\/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|\/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|\/\=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|\+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|\+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|\+\=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|\-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|\-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|\-\=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### Логические операторы  
  
|Name|Синтаксис|  
|----------|---------------|  
|\!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&\=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^\=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;\=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## Заметки  
 Класс `SafeInt` защищает от переполнения целого числа в математических операциях.  Например, рекомендуется рассмотреть 2 8 разрядных целые числа. он имеет значение 200, а второй имеет значение 100.  Правильная математическая операция будет 200 \+ 100 \= 300.  Однако из\-за 8 разрядного целого числа, будет потерян верхний и компилятор возвращает 44 бит \(300 — 2\)<sup>8</sup> как результат.  Любая операция, которая зависит от этого математическом уравнении создает непредвиденное расширения функциональности.  
  
 Класс `SafeInt` проверяет, происходит арифметическое переполнение или ли код пытается разделить ноль.  В обоих случаях класс вызывает обработчик ошибок для предупреждения программы потенциальные проблемы.  
  
 Этот класс также позволяет сравнивать 2 поддерживаются два целых чисел, что они объекты `SafeInt`.  Как правило, при выполнении сравнения, необходимо сначала преобразовать числа, чтобы быть одного типа.  При приведении одного числа в другой тип часто требует проверки убеждают отсутствия потеря данных.  
  
 Таблица операторов в этом разделе перечислены математические и операторы сравнения, поддерживаемые классом `SafeInt`.  Большинство математические операторы возвращают объект `SafeInt` типа `T`.  
  
 Операции сравнения двух `SafeInt` и целочисленным типом могут выполняться в любом направлении.  Например, `SafeInt<int>(x) < y` и `y > SafeInt<int>(x)` допустимый и возвращают одинаковый результат.  
  
 Многие бинарных операторов не поддерживают с помощью 2 различных типов `SafeInt`.  Примером этого оператор `&`.  `SafeInt<T, E> & int` поддерживается, но `SafeInt<T, E> & SafeInt<U, E>` нет.  В последнем примере, компилятор не знает тип параметра, который необходимо вернуть.  Решением этой проблемы приведение второй параметр к базовому типу.  С помощью тех параметров, это можно сделать с `SafeInt<T, E> & (U)SafeInt<U, E>`.  
  
> [!NOTE]
>  Для всех битовых операций 2 различных параметров должны быть одинаковым размером.  Если размеры отличаются, компилятор создает исключение [ASSERT](../Topic/ASSERT%20\(MFC\).md).  Результаты эту операцию нельзя гарантировать, что были явным образом.  Для разрешения этой проблемы выполните приведение меньше параметра до тех пор пока не будет одинаковый размер большей как параметр.  
  
 Для операторов Shift сдвигающ несколько битов, существующие для типа шаблона будут вызывать исключение ASSERT.  Это не будет иметь эффекта в режиме выпуска.  2 Типа комбинации параметров SafeInt возможно для операторов Shift, поскольку тип возвращаемого значения совпадает с исходный тип.  Номер в правой части оператора только показывает количество битов к переносу.  
  
 При выполнении логическое сравнение с объектом SafeInt, сравнение строго арифметический.  Например, рассмотрим следующие выражения:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 Первая выписка разрешение в `true`, а вторая выписка разрешение в `false`.  Побитовое отрицание 0 0xFFFFFFFF.  Во второй инструкцию, оператор сравнения по умолчанию сравнивает 0xFFFFFFFF в 0xFFFFFFFF и проверяет, что они будут равны.  Оператор сравнения для класса `SafeInt` поняли, что второй параметр отрицательный в то время как первый параметр удаляется подпись.  Поэтому, хотя в представление одинаково, логический оператор `SafeInt` поняли, что целое число без знака превышает \-1.  
  
 Будьте внимательны при использовании класса `SafeInt` вместе с оператором `?:` троичным.  Рассмотрим следующую строку кода.  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Компилятор преобразует его в этот:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Если `flag``false`, компилятор создает исключение, а не присвоить значение \-1. `x`.  Поэтому во избежание этого расширения функциональности, правильный код использовать следующую линией.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` и `U` можно присвоить логический тип, внешний вид шрифта, типом или типом.  Целочисленные типы могут быть знаковым или удаление и размер любой из 8 бит на 64 бита.  
  
> [!NOTE]
>  Хотя класс `SafeInt` принимает любой тип целого числа, он выполняет более эффективно с типами без знака.  
  
 `E` механизм обработки ошибок, `SafeInt` использует.  2 Механизм обработки ошибок предоставляются с библиотекой SafeInt.  Политика по умолчанию `SafeIntErrorPolicy_SafeIntException`, которая создает исключение [Класс SafeIntException](../windows/safeintexception-class.md) при возникновении ошибки.  Другая политика `SafeIntErrorPolicy_InvalidParameter`\(остановка программы при возникновении ошибки.  
  
 2 Параметра настраивать политику ошибки.  Первый вариант установить параметр `E` при создании `SafeInt`.  Этот параметр следует использовать, когда требуется изменить политику обработки ошибок только для одного `SafeInt`.  Другой параметр для указания `_SAFEINT_DEFAULT_ERROR_POLICY`, чтобы быть настроенным классом для обработки ошибок, прежде чем включать библиотеку `SafeInt`.  Используйте этот параметр, если необходимо изменить ошибка обработки политики по умолчанию для всех экземпляров класса `SafeInt` в коде.  
  
> [!NOTE]
>  Числом класс, который обрабатывает ошибки из библиотеки SafeInt не должен возвращать элемент управления коду, который вызвал обработчик ошибок.  После того, как обработчик ошибок, называется результату операции `SafeInt` нельзя доверять.  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## См. также  
 [Прочие классы библиотек поддержки](http://msdn.microsoft.com/ru-ru/406fd46e-d53f-4096-ab40-36aa754c7a5c)   
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeIntException](../windows/safeintexception-class.md)