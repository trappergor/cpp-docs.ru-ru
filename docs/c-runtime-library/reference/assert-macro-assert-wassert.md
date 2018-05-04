---
title: Макрос assert, _assert, _wassert | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0318abde877e9b647c1781408d2e22cc9d70824e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="assert-macro-assert-wassert"></a>Макрос assert, _assert, _wassert

Вычисляет выражение и, если результат **false**, выводит диагностическое сообщение и прерывает выполнение программы.

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

*выражение* скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (**true**) или 0 (**false**).

*сообщение* отображаемое сообщение.

*Имя файла* имя исходного файла сбой в утверждения.

*строки* номер строки в исходном файле утверждение, вызвавшее сбой.

## <a name="remarks"></a>Примечания

**Assert** макрос обычно используется для выявления ошибок логики во время разработки программ. Используйте его для остановки выполнения программы при возникновении непредвиденных условий путем реализации *выражение* аргумент, чтобы он принимал значение **false** только если программа работает неправильно. Проверки утверждения можно отключить во время компиляции, определив макрос **NDEBUG**. Можно отключить **assert** макрос без изменения исходных файлов с помощью **/DNDEBUG** параметр командной строки. Можно отключить **assert** макрос в исходном коде с помощью `#define NDEBUG` директиву перед \<assert.h > включено.

**Assert** макрос выводит диагностическое сообщение при *выражение* равен **false** (0) и вызывает метод [прервать](abort.md) завершение программы выполнение. Никакие действия не выполняются, если *выражение* — **true** (не равно нулю). Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.

Диагностическое сообщение выводится в расширенных символах. Таким образом, работа будет выполняться ожидаемым образом, даже если в выражении содержатся символы юникода.

Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения всегда получают сообщения через **stderr**. В приложении Windows **assert** вызывает Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) функцию для создания окна сообщения для отображения сообщения вместе с **ОК** кнопки. Когда пользователь нажимает **ОК**, программа немедленно завершается.

Когда приложение связано с отладочной версией библиотеки времени выполнения, **assert** создает окно сообщения с тремя кнопками: **прервать**, **повторите**и **Игнорировать**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT-отладку программы, если JIT-отладка включена. Если пользователь нажимает кнопку **Ignore**, **assert** продолжает нормальное выполнение: создает окно сообщения с **ОК** кнопки. Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к неожиданному поведению.

Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).

**_Assert** и **_wassert** функции являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Вызывать эти функции напрямую не рекомендуется.

**Assert** макрос включено в отладочной и окончательной версиями библиотеки времени выполнения C при **NDEBUG** не определен. Когда **NDEBUG** будет определен, макрос доступен, но его аргумент не вычисляется и не оказывает влияния. Если он включен, **assert** вызовов макросов **_wassert** для его реализации. Другие макросы утверждения, [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) и [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [_DEBUG](../../c-runtime-library/debug.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Assert**, **_wassert**|\<assert.h>|

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
