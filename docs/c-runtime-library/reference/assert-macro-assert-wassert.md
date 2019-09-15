---
title: Макрос assert, _assert, _wassert
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
ms.openlocfilehash: badca46a0793e51602f0de87dfca21816dcd6295
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939617"
---
# <a name="assert-macro-_assert-_wassert"></a>Макрос assert, _assert, _wassert

Вычисляет выражение и, если результат равен **false**, выводит диагностическое сообщение и прерывает выполнение программы.

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
Скалярное выражение (включая выражения указателей), результатом которого является ненулевое**значение (true**) или 0 (**false**).

*message*<br/>
Отображаемое сообщение.

*filename*<br/>
Имя файла исходного кода, в котором произошел сбой утверждения.

*штрих*<br/>
Номер строки в файле исходного кода, в которой произошел сбой утверждения.

## <a name="remarks"></a>Примечания

Макрос **Assert** обычно используется для обнаружения логических ошибок во время разработки программы. Используйте его для того, чтобы предотвратить выполнение программы при непредвиденных условиях, реализовав аргумент *выражения* для вычисления значения **false** только в том случае, если программа работает неправильно. Проверка утверждения может быть отключена во время компиляции путем определения макроса **NDEBUG**. Макрос **Assert** можно отключить, не изменяя исходные файлы с помощью параметра командной строки **/дндебуг** . Макрос **Assert** можно отключить в исходном коде с помощью `#define NDEBUG` директивы, прежде чем \<будет включен Assert. h >.

Макрос **Assert** выводит диагностическое сообщение, когда *выражение* принимает **значение false** (0) и вызывает [Abort](abort.md) для завершения выполнения программы. Если *выражение* имеет **значение true** (отличное от нуля), никакие действия не выполняются. Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.

Диагностическое сообщение выводится в расширенных символах. Таким образом, работа будет выполняться ожидаемым образом, даже если в выражении содержатся символы юникода.

Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения всегда получают сообщение через **stderr**. В приложении на базе Windows метод **Assert** вызывает функцию Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) , чтобы создать окно сообщения для вывода сообщения и кнопки **ОК** . Когда пользователь нажимает **ОК**, программа немедленно завершается.

Когда приложение связывается с отладочной версией библиотек времени выполнения, **Assert** создает окно сообщения с тремя кнопками: **Прервать**, **повторить**и **пропустить**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT-отладку программы, если JIT-отладка включена. Если пользователь нажмет кнопку **пропустить**, **Assert** будет продолжать нормальное выполнение: создание окна сообщения с кнопкой **ОК** . Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к неожиданному поведению.

Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).

Функции **_ASSERT** и **_wassert** являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Вызывать эти функции напрямую не рекомендуется.

Макрос **Assert** включается в версиях выпуска и отладки библиотек времени выполнения C, если **NDEBUG** не определен. Если определен **NDEBUG** , макрос доступен, но не вычисляет его аргумент и не оказывает никакого влияния. Если он включен, макрос **Assert** вызывает **_wassert** для своей реализации. Другие макросы утверждения, [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) и [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [_DEBUG](../../c-runtime-library/debug.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Assert**, **_wassert**|\<assert.h>|

Сигнатура функции **_ASSERT** недоступна в файле заголовка. Сигнатура функции **_wassert** доступна только в том случае, если макрос **NDEBUG** не определен.

## <a name="example"></a>Пример

В этой программе функция **analyze_string** использует макрос **Assert** для проверки нескольких условий, связанных со строкой и длиной. Если какое-либо из условий не выполняется, программа выводит сообщение, указывающее на причину сбоя.

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

После сбоя утверждения вы можете увидеть сообщение наподобие приведенного ниже (точный текст зависит от версии операционной системы и библиотеки среды выполнения).

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Если отладчик установлен, нажмите кнопку **Отладка** , чтобы запустить его, или кнопку **Закрыть программу** , чтобы выйти.

## <a name="see-also"></a>См. также

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
