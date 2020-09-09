---
title: Макрос assert, _assert, _wassert
description: Влияние макросов и функций Assert в среде выполнения C.
ms.date: 11/04/2016
api_name:
- assert
- _assert
- _wassert
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
ms.openlocfilehash: 071424f2201ceda43438fe1056801811fe444a01
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609083"
---
# <a name="assert-macro-_assert-_wassert"></a>Макрос assert, _assert, _wassert

Вычисляет выражение и, если результат имеет значение **`false`** , выводит диагностическое сообщение и прерывает программу.

## <a name="syntax"></a>Синтаксис

```C
assert(
   expression
);
void _assert(
   char const* message,
   char const* filename,
   unsigned line
);
void _wassert(
   wchar_t const* message,
   wchar_t const* filename,
   unsigned line
);
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Скалярное выражение (включая выражения указателей), результатом которого является ненулевое значение ( **`true`** ) или 0 ( **`false`** ).

*message*<br/>
Отображаемое сообщение.

*filename*<br/>
Имя файла исходного кода, в котором произошел сбой утверждения.

*line*<br/>
Номер строки в файле исходного кода, в которой произошел сбой утверждения.

## <a name="remarks"></a>Примечания

Макрос `assert` обычно используется для выявления ошибок логики во время разработки программы. Используйте его для того, чтобы предотвратить выполнение программы при непредвиденных условиях, реализовав аргумент *выражения* для вычисления **`false`** только в случае неправильной работы программы. Проверка утверждения может быть отключена во время компиляции путем определения макроса **NDEBUG**. Вы можете отключить макрос `assert` , не изменяя файлы исходного кода, с помощью параметра командной строки **/DNDEBUG** . Вы можете отключить `assert` макрос в исходном коде, используя `#define NDEBUG` директиву перед \<assert.h> включением.

`assert`Макрос выводит диагностическое сообщение, когда *выражение* принимает значение **`false`** (0) и вызывает метод [`abort`](abort.md) для завершения выполнения программы. Если *выражение* имеет значение **`true`** (отличное от нуля), никакие действия не выполняются. Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.

Диагностическое сообщение печатается в расширенных `wchar_t` символах (). Поэтому он будет работать должным образом даже в том случае, если в выражении есть символы Юникода.

Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения получают сообщение через **stderr**. В приложении Windows `assert` вызывает функцию Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) , чтобы создать окно сообщения для вывода на экран сообщения с тремя кнопками: **Abort**, **Retry**и **Ignore**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT-отладку программы, если JIT-отладка включена. Если пользователь нажмет кнопку **пропустить**, программа продолжит нормальное выполнение. Нажатие кнопки **пропустить** при наличии состояния ошибки может привести к неопределенному поведению, поскольку предварительные условия вызывающего кода не выполнены.

Чтобы переопределить поведение вывода по умолчанию независимо от типа приложения, вызовите метод [`_set_error_mode`](set-error-mode.md) для выбора между выходом вывода в stderr и отображением диалогового окна.

После `assert` отображения сообщения он вызывает метод [`abort`](abort.md) , который отображает диалоговое окно с кнопками  **прервать**, **повторить**и **пропустить** . [`abort`](abort.md) завершает программу, поэтому кнопка **повторить** и **пропустить** не возобновляет выполнение программы после `assert` вызова. Если `assert` отображается диалоговое окно, [`abort`](abort.md) диалоговое окно не отображается. [`abort`](abort.md)Диалоговое окно отображается только при `assert` отправке выходных данных в stderr.

Как следствие приведенного выше поведения, диалоговое окно всегда отображается после `assert` вызова в режиме отладки. Поведение каждой кнопки захватывается в таблице ниже.

|Режим ошибок|Вывод в stderr (консоль/_OUT_TO_STDERR)|Диалоговое окно «Отображение» (Windows/_OUT_TO_MSGBOX)|
|----------|----------------|------------------|
|Прерывание|Немедленное завершение работы с кодом выхода 3|Немедленное завершение работы с кодом выхода 3|
|Повторить попытку|Прерывать в отладчике во время `abort`|Прерывать в отладчике во время `assert`|
|Игнорировать|Завершить выход через `abort`|Продолжить выполнение программы, как будто утверждение не активировалось (может привести к неопределенному поведению, так как предусловия вызывающего кода не выполнены)|

Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).

Функции `_assert` и `_wassert` являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Мы не рекомендуем вызывать эти функции напрямую.

`assert`Макрос включается в версиях выпуска и отладки библиотек времени выполнения C, если **NDEBUG** не определен. Если определен **NDEBUG** , макрос доступен, но не вычисляет его аргумент и не оказывает никакого влияния. Если он включен, `assert` макрос вызывает метод `_wassert` для его реализации. Другие макросы утверждения, [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) и [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [_DEBUG](../../c-runtime-library/debug.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`assert`, `_wassert`|\<assert.h>|

Сигнатура `_assert` функции недоступна в файле заголовка. Сигнатура `_wassert` функции доступна, только если не определен макрос **NDEBUG** .

## <a name="example"></a>Пример

В этой программе функция **analyze_string** использует `assert` макрос для проверки нескольких условий, связанных со строкой и длиной. Если какое-либо из условий не выполняется, программа выводит сообщение, указывающее на причину сбоя.

```C
// crt_assert.c
// compile by using: cl /W4 crt_assert.c
#include <stdio.h>
#include <assert.h>
#include <string.h>

void analyze_string( char *string );   // Prototype

int main( void )
{
   char  test1[] = "abc", *test2 = NULL, test3[] = "";

   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );
   analyze_string( test1 );
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );
   analyze_string( test2 );
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );
   analyze_string( test3 );
}

// Tests a string to see if it is NULL,
// empty, or longer than 0 characters.
void analyze_string( char * string )
{
   assert( string != NULL );        // Cannot be NULL
   assert( *string != '\0' );       // Cannot be empty
   assert( strlen( string ) > 2 );  // Length must exceed 2
}
```

Программа создает следующие выходные данные:

```Output
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

После сбоя утверждения в зависимости от версии операционной системы и библиотеки времени выполнения может появиться окно сообщения, содержащее примерно следующее:

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Если отладчик установлен, нажмите кнопку **Отладка** , чтобы запустить его, или кнопку **Закрыть программу** , чтобы выйти.

## <a name="see-also"></a>См. также раздел

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[рвал](abort.md)<br/>
[вести](raise.md)<br/>
[signal](signal.md);<br/>
[Макросы _ASSERT, _ASSERTE и _ASSERT_EXPR](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
