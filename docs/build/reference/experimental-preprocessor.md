---
title: '/експериментал: препроцессор (Включение режима соответствия препроцессора)'
description: 'Используйте параметр компилятора/експериментал: препроцессора, чтобы включить экспериментальную поддержку компилятора для стандартного соответствия препроцессору.'
ms.date: 09/03/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 3055cfa2a32d1d668dbe0c51b5542415b5bb0af4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294441"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/експериментал: препроцессор (Включение режима соответствия препроцессора)

Этот параметр включает экспериментальный препроцессор на основе маркеров, который соответствует стандартам C++ 11, включая функции препроцессора C99.

## <a name="syntax"></a>Синтаксис

> **/експериментал: препроцессор** [ **-** ]

## <a name="remarks"></a>Примечания

Используйте параметр компилятора **/експериментал: препроцессора** , чтобы включить экспериментальный препроцессор. Для явного указания традиционного препроцессора можно использовать **/експериментал: препроцессор** .

Параметр **/експериментал: препроцессор** доступен начиная с Visual Studio 2017 версии 15,8.

Вы можете определить, какой препроцессор используется во время компиляции. Проверьте значение предопределенного макроса [ \_компилятором MSVC\_традиционный](../../preprocessor/predefined-macros.md) , чтобы узнать, используется ли традиционный препроцессор. Этот макрос задается в неусловном состоянии по версиям компилятора, поддерживающих его, независимо от того, какой препроцессор вызывается. Его значение равно 1 для традиционного препроцессора. Это 0 для согласованного экспериментального препроцессора:

```cpp
#if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
// Logic using the traditional preprocessor
#else
// Logic using cross-platform compatible preprocessor
#endif
```

### <a name="behavior-changes-in-the-experimental-preprocessor"></a>Изменения в поведении экспериментального препроцессора

Ниже приведены некоторые из наиболее распространенных критических изменений, обнаруженных при включении режима соответствия препроцессору.

#### <a name="macro-comments"></a>Комментарии макроса

Традиционный препроцессор использует символьные буферы вместо токенов препроцессора. Это обеспечивает некоторое необычное поведение, такое как этот прием комментария препроцессора, который не работает в соответствии с препроцессором:

```cpp
#if DISAPPEAR
#define DISAPPEARING_TYPE /##/
#else
#define DISAPPEARING_TYPE int
#endif

// myVal disappears when DISAPPEARING_TYPE is turned into a comment
// To make standards compliant, wrap the following line with the appropriate #if/#endif
DISAPPEARING_TYPE myVal;
```

#### <a name="string-prefixes-lval"></a>Префиксы строк (L # Val)

Традиционный препроцессор неправильно объединяет префикс строки в результат [оператора строковый (#)](../../preprocessor/stringizing-operator-hash.md):

```cpp
#define DEBUG_INFO(val) L"debug prefix:" L#val
//                                       ^
//                                       this prefix

const wchar_t *info = DEBUG_INFO(hello world);
```

`L` Префикс не нужен здесь, так как соседние строковые литералы в любом случае объединяются после расширения макроса. Обратная совместимость исправления заключается в том, чтобы изменить определение на:

```cpp
#define DEBUG_INFO(val) L"debug prefix:" #val
//                                       ^
//                                       no prefix
```

Эта проблема также обнаружена в удобных макросах, которые "строчный" аргумент к расширенному строковому литералу:

```cpp
// The traditional preprocessor creates a single wide string literal token
#define STRING(str) L#str

// Potential fixes:
// Use string concatenation of L"" and #str to add prefix
// This works because adjacent string literals are combined after macro expansion
#define STRING1(str) L""#str

// Add the prefix after #str is stringized with additional macro expansion
#define WIDE(str) L##str
#define STRING2(str) WIDE(#str)

// Use concatenation operator ## to combine the tokens.
// The order of operations for ## and # is unspecified, although all compilers
// checked perform the # operator before ## in this case.
#define STRING3(str) L## #str
```

#### <a name="warning-on-invalid"></a>Предупреждение при недопустимом ##

Если [оператор, искрывающий токен (# #)](../../preprocessor/token-pasting-operator-hash-hash.md) , не приводит к созданию единственного допустимого маркера предварительной обработки, поведение не определено. Традиционному препроцессору не удается автоматически объединить маркеры. Новый препроцессор соответствует поведению большинства других компиляторов и создает диагностику.

```cpp
// The ## is unnecessary and doesn't result in a single preprocessing token.
#define ADD_STD(x) std::##x

// Declare a std::string
ADD_STD(string) s;
```

#### <a name="comma-elision-in-variadic-macros"></a>Элизии с запятыми в макросах Variadic

Рассмотрим следующий пример.

```cpp
void func(int, int = 2, int = 3);
// This macro replacement list has a comma followed by __VA_ARGS__
#define FUNC(a, ...) func(a, __VA_ARGS__)
int main()
{
    // The following macro is replaced with:
    // func(10,20,30)
    FUNC(10, 20, 30);

    // A conforming preprocessor replaces the following macro with:
    // func(1, );
    // which results in a syntax error.
    FUNC(1, );
}
```

Все основные компиляторы имеют расширение препроцессора, помогающее решить эту проблемы. Традиционный препроцессор компилятором MSVC всегда удаляет запятые перед пустыми `__VA_ARGS__` заменами. Обновленный препроцессор более полно соответствует поведению других популярных межплатформенных компиляторов. Чтобы удалить запятую, аргумент Variadic должен быть пропущен, а не просто пустым и должен быть помечен `##` оператором:

```cpp
#define FUNC2(a, ...) func(a , ## __VA_ARGS__)
int main()
{
    // The variadic argument is missing in the macro being evoked
    // The comma is removed and replaced with:
    // func(1)
    FUNC2(1);

    // The variadic argument is empty, but not missing. (Notice the
    // comma in the argument list.) The comma isn't removed
    // when the macro is replaced:
    // func(1, )
    FUNC2(1, );
}
```

В предстоящем стандарте C + + 2A эта проблема была устранена путем добавления `__VA_OPT__`, которая еще не реализована.

#### <a name="macro-arguments-are-unpacked"></a>Аргументы макроса "распаковано"

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

При развертывании `A()`традиционный препроцессор пересылает все аргументы, Упакованные в `__VA_ARGS__` , в первый аргумент `TWO_STRINGS`. Аргумент `TWO_STRINGS` Variadic пуст, что приводит `#first` к `"1, 2"` результату, а не просто `"1"`. Возможно, вас интересует, что произошло с результатом `#__VA_ARGS__` традиционного расширения препроцессора. Если параметр Variadic пуст, он должен привести к созданию пустого строкового литерала "". Из-за отдельной проблемы токен пустого строкового литерала не был создан.

#### <a name="rescanning-replacement-list-for-macros"></a>Повторное сканирование списка замен для макросов

После замены макроса полученные маркеры повторно проверяются на наличие дополнительных идентификаторов макросов для замены. Алгоритм повторного сканирования, используемый традиционным препроцессором, не соответствует, как показано в этом примере на основе фактического кода:

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

Чтобы увидеть, что происходит в этом примере, мы разберем расширение, начинающееся с `DO_THING`:

`DO_THING(1, "World")` ->
`CAT(IMPL, 1) ECHO(("Hello", "World"))`

Во-вторых, CAT расширяется:

`CAT(IMPL, 1)` -> `IMPL ## 1` -> `IMPL1`

Который помещает маркеры в это состояние:

`IMPL1 ECHO(("Hello", "World"))`

Препроцессор находит идентификатор `IMPL1`макроса, аналогичного функции, но за ним не следует символ "(", поэтому он не считается вызовом макроса, похожего на функцию. Он переходит к следующим маркерам и находит вызов макроса `ECHO` , похожего на функцию:

`ECHO(("Hello", "World"))` -> `("Hello", "World")`

`IMPL1`не считается повторно для расширения, поэтому полный результат расширения будет следующим:

`IMPL1("Hello", "World");`

Макрос можно изменить таким же образом, как и в экспериментальной предварительной обработке, и в традиционном препроцессоре. Решение заключается в добавлении другого уровня косвенного обращения:

```cpp
#define CAT(a,b) a##b
#define ECHO(...) __VA_ARGS__

// IMPL1 and IMPL2 are macros implementation details
#define IMPL1(prefix,value) do_thing_one( prefix, value)
#define IMPL2(prefix,value) do_thing_two( prefix, value)

#define CALL(macroName, args) macroName args
#define DO_THING_FIXED(a,b) CALL( CAT(IMPL, a), ECHO(( "Hello",b)))

DO_THING_FIXED(1, "World");
// macro expanded to:
// do_thing_one( "Hello", "World");
```

### <a name="conformance-mode-conformance"></a>Соответствие режима соответствия

Экспериментальный препроцессор еще не завершен, а часть логики директив препроцессора по-прежнему переходит к традиционному поведению. Ниже приведен частичный список незавершенных функций.

- Поддержка`_Pragma`
- Функции c++ 20
- Дополнительные диагностические улучшения
- Переключение для управления выводом в разделе/E и/P
- Ошибка блокировки повышения: Логические операторы в выражениях констант препроцессора не полностью реализованы в новом препроцессоре. В некоторых `#if` директивах новый препроцессор может вернуться к традиционному препроцессору. Этот результат заметен только в том случае, если макросы, несовместимые с традиционным препроцессором, развернуты, что может произойти при создании слотов препроцессора для повышения.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++**  > **Командная строка**.

1. Измените свойство **Дополнительные параметры** , включив в него **/експериментал: препроцессор** , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)
