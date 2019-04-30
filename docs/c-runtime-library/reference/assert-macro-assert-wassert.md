---
title: Макрос assert, _assert, _wassert
ms.date: 11/04/2016
apiname:
- assert
- _assert
- _wassert
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 7ac299213ba3de878f7cf2dc99b44c45273bc3b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341370"
---
# <a name="assert-macro-assert-wassert"></a>Макрос assert, _assert, _wassert

Вычисляет выражение и, если результат — **false**, выводит диагностическое сообщение и прерывает выполнение программы.

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

*Выражение*<br/>
Скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (**true**) или 0 (**false**).

*message*<br/>
Отображаемое сообщение.

*filename*<br/>
Имя файла исходного кода, в котором произошел сбой утверждения.

*Строки*<br/>
Номер строки в файле исходного кода, в которой произошел сбой утверждения.

## <a name="remarks"></a>Примечания

**Assert** макрос обычно используется для выявления ошибок логики во время разработки программ. Используйте его для остановки выполнения программы при возникновении непредвиденных условий путем реализации *выражение* аргумент для вычисления **false** только при некорректной работе программы. Проверки утверждения можно отключить во время компиляции, определив макрос **NDEBUG**. Вы можете отключить **assert** макрос без изменения исходных файлов с помощью **/DNDEBUG** параметр командной строки. Вы можете отключить **assert** макрос в исходном коде, с помощью `#define NDEBUG` директиву перед \<assert.h > включен.

**Assert** макрос выводит диагностическое сообщение при *выражение* принимает значение **false** (0) и вызывает метод [прервать](abort.md) завершение программы выполнение. Никакие действия не выполняются, если *выражение* — **true** (не равно нулю). Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.

Диагностическое сообщение выводится в расширенных символах. Таким образом, работа будет выполняться ожидаемым образом, даже если в выражении содержатся символы юникода.

Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения всегда получают сообщения через **stderr**. В приложении на базе Windows **assert** вызывает Windows [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) функцию для создания окна сообщения для отображения сообщения вместе с **ОК** кнопки. Когда пользователь нажимает **ОК**, программа немедленно завершается.

Когда приложение связано с отладочной версией библиотек времени выполнения, **assert** создает окно сообщения с тремя кнопками: **Прервать**, **повторите**, и **игнорировать**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT-отладку программы, если JIT-отладка включена. Если пользователь нажимает кнопку **пропустить**, **assert** продолжает нормальное выполнение: создает окно сообщения с **ОК** кнопки. Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к неожиданному поведению.

Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).

**_Assert** и **_wassert** функции являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Вызывать эти функции напрямую не рекомендуется.

**Assert** макрос включен в отладочной и окончательной версиях библиотек времени выполнения C при **NDEBUG** не определен. Когда **NDEBUG** будет определен, макрос доступен, но его аргумент не вычисляется и не оказывает влияния. Если он включен, **assert** вызовов макросов **_wassert** для его реализации. Другие макросы утверждения, [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) и [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [_DEBUG](../../c-runtime-library/debug.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**assert**, **_wassert**|\<assert.h>|

Подпись **_assert** функция недоступна в файле заголовка. Подпись **_wassert** функция доступна только тогда, когда **NDEBUG** макрос не определен.

## <a name="example"></a>Пример

В этой программе **analyze_string** функция использует **assert** макрос для проверки нескольких условий, связанных со строкой и длиной. Если какое-либо из условий не выполняется, программа выводит сообщение, указывающее на причину сбоя.

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
