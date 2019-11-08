---
title: Обзор экспериментального препроцессора КОМПИЛЯТОРОМ MSVC
description: Препроцессор КОМПИЛЯТОРОМ MSVC обновляется для соответствия стандартам C/C++ Standard.
ms.date: 11/06/2019
helpviewer_keywords:
- preprocessor, experimental
ms.openlocfilehash: 446603b34d9309c256afba9abd7234ae2ab16f5c
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73797190"
---
# <a name="msvc-experimental-preprocessor-overview"></a>Обзор экспериментального препроцессора КОМПИЛЯТОРОМ MSVC

В настоящее C++ время препроцессор Майкрософт обновляется для улучшения соответствия стандартам, устранения ошибок всегда и изменения некоторых поведений, которые официально не определены. Кроме того, добавлены новые средства диагностики для предупреждения об ошибках в определениях макросов.

Эти изменения в их текущем состоянии доступны с помощью переключателя компилятора [/експериментал: препроцессора](../build/reference/experimental-preprocessor.md) в visual Studio 2017 или visual Studio 2019. Поведение препроцессора по умолчанию остается таким же, как и в предыдущих версиях.

## <a name="new-predefined-macro"></a>Новый предопределенный макрос

Вы можете определить, какой препроцессор используется во время компиляции. Проверьте значение предопределенного макроса [\_компилятором msvc\_традиционный](predefined-macros.md) , чтобы узнать, используется ли традиционный препроцессор. Этот макрос задается в неусловном состоянии по версиям компилятора, поддерживающих его, независимо от того, какой препроцессор вызывается. Его значение равно 1 для традиционного препроцессора. Это 0 для согласованного экспериментального препроцессора:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

## <a name="behavior-changes-in-the-experimental-preprocessor"></a>Изменения в поведении экспериментального препроцессора

Начальная работа в экспериментальной предварительной версии была сосредоточена на обеспечении соответствия всех расширений макросов, чтобы использовать компилятор КОМПИЛЯТОРОМ MSVC с библиотеками, заблокированными в данный момент из-за традиционных поведений. Ниже приведен список некоторых из наиболее распространенных критических изменений, которые были выполнены при тестировании обновленной предварительной версии с реальными проектами мира.

### <a name="macro-comments"></a>Комментарии макроса

Традиционный препроцессор основан на символьных буферах, а не на маркерах препроцессора. Это обеспечивает необычное поведение, например следующий прием комментария препроцессора, который не будет работать в соответствии с препроцессором:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
DISAPPEARING_TYPE myVal;
```

Стандартным исправлением является объявление `int myVal` в соответствующих директивах `#ifdef/#endif`:

```cpp
#define MYVAL 1

#ifdef MYVAL
int myVal;
#endif
```

### <a name="lval"></a>L # Val

Традиционный препроцессор неправильно объединяет префикс строки в результат оператора [строковый operator (#)](stringizing-operator-hash.md) :

```cpp
 #define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

В этом случае префикс `L` не нужен, так как соседние строковые литералы объединяются после расширения макроса. Исправление обратной совместимости заключается в том, чтобы изменить определение следующим образом:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Эта же ситуация также возникает в удобных макросах, которые «строчный» аргумент к расширенному строковому литералу:

```cpp
 // The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str
```

Устранить проблему можно различными способами.

- Для добавления префикса используйте объединение строк `L""` и `#str`. Это работает потому, что соседние строковые литералы объединяются после расширения макроса:

   ```cpp
   #define STRING1(str) L""#str
   ```

- Добавление префикса после `#str` в виде строки с дополнительным расширением макроса

   ```cpp
   #define WIDE(str) L##str
   #define STRING2(str) WIDE(#str)
   ```

- Используйте оператор объединения `##`, чтобы объединить токены. Порядок операций для `##` и `#` не задан, хотя все компиляторы кажутся оценивать оператор `#` перед тем, как в этом случае `##`.

   ```cpp
   #define STRING3(str) L## #str
   ```

### <a name="warning-on-invalid-"></a>Предупреждение при недопустимом \#\#

Если оператор, выполняющий выход из [токена (# #)](token-pasting-operator-hash-hash.md) , не содержит один допустимый токен предварительной обработки, поведение не определено. Традиционный препроцессор не будет автоматически объединять маркеры. Новый препроцессор будет соответствовать поведению большинства других компиляторов и выдавать диагностику.

```cpp
// The ## is unnecessary and does not result in a single preprocessing token.
#define ADD_STD(x) std::##x
// Declare a std::string
ADD_STD(string) s;
```

### <a name="comma-elision-in-variadic-macros"></a>Элизии с запятыми в макросах Variadic

Традиционный препроцессор КОМПИЛЯТОРОМ MSVC всегда удаляет запятые перед пустыми `__VA_ARGS__` замены. Экспериментальный препроцессор более полно соответствует поведению других популярных межплатформенных компиляторов. Чтобы удалить запятую, аргумент Variadic должен быть пропущен (не просто пустой) и должен быть помечен оператором `##`. Рассмотрим следующий пример.

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // In the traditional preprocessor, the following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor will replace the following macro with: func(1, ), which will result in a syntax error.
    FUNC(1, );
}
```

В следующем примере в вызове `FUNC2(1)` аргумент Variadic отсутствует в евокед макросе. В вызове `FUNC2(1, )` аргумент Variadic пуст, но отсутствует (Обратите внимание на запятую в списке аргументов).

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
   // Expands to func(1)
   FUNC2(1);

   // Expands to func(1, )
   FUNC2(1, );
}
```

В предстоящем стандарте C + + 2A эта проблема устранена путем добавления `__VA_OPT__`, которая еще не реализована.

### <a name="macro-arguments-are-unpacked"></a>Аргументы макроса являются распакованными

В традиционном препроцессоре, если макрос пересылает один из своих аргументов другому зависимому макросу, аргумент не получает «распакованный» при замене. Обычно такая оптимизация незаметна, но может привести к необычному поведению:

```cpp
// Create a string out of the first argument, and the rest of the arguments.
#define TWO_STRINGS( first, ... ) #first, #__VA_ARGS__
#define A( ... ) TWO_STRINGS(__VA_ARGS__)
const char* c[2] = { A(1, 2) };

// Conformant preprocessor results:
// const char c[2] = { "1", "2" };

// Traditional preprocessor results, all arguments are in the first string:
// const char c[2] = { "1, 2", };
```

При развертывании `A()`традиционный препроцессор пересылает все аргументы, Упакованные в `__VA_ARGS__`, в первый аргумент TWO_STRINGS, который оставляет аргумент Variadic в `TWO_STRINGS` пустым. Это приводит к тому, что результатом `#first` будет "1, 2", а не просто "1". При внимательном рассмотрении может возникнуть вопрос, что произошло с результатом `#__VA_ARGS__` в традиционном расширении препроцессора: Если параметр Variadic пуст, он должен привести к `""`у пустого строкового литерала. Из-за отдельной проблемы токен пустого строкового литерала не был создан.

### <a name="rescanning-replacement-list-for-macros"></a>Повторное сканирование списка замен для макросов

После замены макроса полученные маркеры повторно проверяются на наличие дополнительных идентификаторов макросов, которые необходимо заменить. Алгоритм, используемый традиционным препроцессором для выполнения повторного сканирования, не является согласованным, как показано в этом примере на основе фактического кода:

```cpp
#define CAT(a,b) a ## b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

// MACRO chooses the expansion behavior based on the value passed to macro_switch
#define DO_THING(macro_switch, b) CAT(IMPL, macro_switch) ECHO(( "Hello", b))
DO_THING(1, "World");

// Traditional preprocessor:
// do_thing_one( "Hello", "World");
// Conformant preprocessor:
// IMPL1 ( "Hello","World");
```

Хотя этот пример кажется надуманныйным, он был обнаружен в реальном мире кода. Чтобы увидеть, что происходит, можно разбить расширение на `DO_THING`:

1. `DO_THING(1, "World")` разворачивается в `CAT(IMPL, 1) ECHO(("Hello", "World"))`
1. `CAT(IMPL, 1)` разворачивается для `IMPL ## 1`, который разворачивается в `IMPL1`
1. Теперь маркеры находятся в этом состоянии: `IMPL1 ECHO(("Hello", "World"))`
1. Препроцессор находит идентификатор макроса, аналогичного функции, `IMPL1`, но за ним не следует `(`, поэтому он не считается вызовом макроса, аналогичного функции. 
1. Он переходит к следующим маркерам и находит макрос, подобный функции, `ECHO` вызываться: `ECHO(("Hello", "World"))`, который разворачивается в `("Hello", "World")`
1. `IMPL1` не считается снова для расширения, поэтому полный результат расширения будет следующим: `IMPL1("Hello", "World");`

Макрос можно изменить в соответствии с экспериментальным препроцессором и традиционным препроцессором, добавив в другой уровень косвенного обращения:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__
// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)
#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))
DO_THING_FIXED(1, "World");

// macro expands to:
// do_thing_one( "Hello", "World");
```

## <a name="incomplete-features"></a>Незавершенные функции

Экспериментальный препроцессор в основном завершен, хотя некоторые логики директив препроцессора по-прежнему находятся в традиционном поведении. Ниже приведен частичный список незавершенных функций.

- Поддержка `_Pragma`
- Функции c++ 20
- Устранение ошибки блокировки. логические операторы в выражениях констант препроцессора не полностью реализованы в новом препроцессоре. В некоторых директивах `#if` новый препроцессор может вернуться к традиционному препроцессору. Этот результат заметен только в том случае, если макросы, несовместимые с традиционным препроцессором, развернуты, что может произойти при создании слотов препроцессора для повышения.
