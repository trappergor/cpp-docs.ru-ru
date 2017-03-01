---
title: "Макрос assert, _assert, _wassert | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ad3410852975757c34220e2de19f696ba3b7c718
ms.lasthandoff: 02/24/2017

---
# <a name="assert-macro-assert-wassert"></a>Макрос assert, _assert, _wassert
Вычисляет выражение и, если результат `false`, выводит диагностическое сообщение и прерывает выполнение программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `expression`  
 Скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (`true`) или 0 (`false`).  
  
 `message`  
 Отображаемое сообщение.  
  
 `filename`  
 Имя файла исходного кода, в котором произошел сбой утверждения.  
  
 `line`  
 Номер строки в файле исходного кода, в которой произошел сбой утверждения.  
  
## <a name="remarks"></a>Примечания  
 Макрос `assert` обычно используется для выявления ошибок логики во время разработки программы. Используйте его для остановки выполнения программы при возникновении непредвиденных условий. Для этого реализуйте аргумент `expression` так, чтобы он принимал значение `false` только в том случае, если программа работает неправильно. Проверки утверждения можно отключить во время компиляции, определив макрос `NDEBUG`. Вы можете отключить макрос `assert` , не изменяя файлы исходного кода, с помощью параметра командной строки **/DNDEBUG** . Чтобы отключить макрос `assert` в исходном коде, используйте директиву `#define NDEBUG` перед включением файла \<assert.h>.  
  
 Макрос `assert` выводит диагностическое сообщение при `expression` равном `false` (0) и вызывает функцию [abort](../../c-runtime-library/reference/abort.md), чтобы прервать выполнение программы. Если значение `expression` равно `true` (отлично от нуля), никаких действий не выполняется. Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.  
  
 Диагностическое сообщение выводится в расширенных символах. Таким образом, работа будет выполняться ожидаемым образом, даже если в выражении содержатся символы юникода.  
  
 Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения всегда получают сообщения через `stderr`. В приложении на основе Windows `assert` вызывает функцию Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) для создания окна сообщения для отображения сообщения вместе с кнопкой **ОК** . Когда пользователь нажимает **ОК**, программа немедленно завершается.  
  
 Когда приложение связывается с отладочной версией библиотеки среды выполнения, `assert` создает окно сообщения с тремя кнопками: **Прервать**, **Повторить**и **Пропустить**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT-отладку программы, если JIT-отладка включена. Если пользователь нажимает кнопку **Пропустить**, `assert` продолжает нормальное выполнение: создает окно сообщения с кнопкой **ОК** . Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к неожиданному поведению.  
  
 Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
 Функции `_assert` и `_wassert` являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Вызывать эти функции напрямую не рекомендуется.  
  
 Макрос `assert` включен и в окончательной, и в отладочной версиях библиотек среды выполнения C, если `NDEBUG` не определен. Если `NDEBUG` определен, макрос доступен, но его аргумент не вычисляется и макрос не оказывает никакого действия. Если макрос `assert` включен, он вызывает `_wassert` для своей реализации. Другие макросы утверждения, [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) и [_ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [_DEBUG](../../c-runtime-library/debug.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`assert`, `_wassert`|\<assert.h>|  
  
 Сигнатура функции `_assert` не доступна в файле заголовка. Сигнатура функции `_wassert` доступна только в том случае, если макрос `NDEBUG` не определен.  
  
## <a name="example"></a>Пример  
 В этой программе функция `analyze_string` использует макрос `assert` для проверки нескольких условий, связанных со строкой и длиной. Если какое-либо из условий не выполняется, программа выводит сообщение, указывающее на причину сбоя.  
  
```  
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
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [Макрос _ASSERT, _ASSERTE, _ASSERT_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
