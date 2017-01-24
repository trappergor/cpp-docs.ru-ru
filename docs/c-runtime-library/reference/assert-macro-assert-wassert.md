---
title: "Макрос assert, _assert, _wassert | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "assert"
  - "_assert"
  - "_wassert"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "assert"
  - "_assert"
  - "_wassert"
  - "assert/_wassert"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "прерывание программ"
  - "assert - функция"
  - "макрос assert"
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Макрос assert, _assert, _wassert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляет выражение и, если результат `false`, выводит диагностическое сообщение и прерывает выполнение программы.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `expression`  
 Скалярное выражение \(включая выражения указателя\), которое возвращает ненулевое значение \(`true`\) или 0 \(`false`\).  
  
 `message`  
 Отображаемое сообщение.  
  
 `filename`  
 Имя файла исходного кода, в котором произошел сбой утверждения.  
  
 `line`  
 Номер строки в файле исходного кода, в которой произошел сбой утверждения.  
  
## Заметки  
 Макрос `assert` обычно используется для выявления ошибок логики во время разработки программы. Используйте его для остановки выполнения программы при возникновении непредвиденных условий. Для этого реализуйте аргумент `expression` так, чтобы он принимал значение `false` только в том случае, если программа работает неправильно. Проверки утверждения можно отключить во время компиляции, определив макрос `NDEBUG`. Можно отключить `assert` макрос без изменения исходных файлов с помощью **\/DNDEBUG** параметр командной строки. Чтобы отключить макрос `assert` в исходном коде, используйте директиву `#define NDEBUG` перед включением файла \<assert.h\>.  
  
 Макрос `assert` выводит диагностическое сообщение при `expression` равном `false` \(0\) и вызывает функцию [abort](../../c-runtime-library/reference/abort.md), чтобы прервать выполнение программы. Если значение `expression` равно `true` \(отлично от нуля\), никаких действий не выполняется. Диагностическое сообщение включает выражение, где произошел сбой, имя файла исходного кода и номер строки, со сбоем утверждения.  
  
 Диагностическое сообщение выводится в расширенных символах. Таким образом, работа будет выполняться ожидаемым образом, даже если в выражении содержатся символы юникода.  
  
 Назначение диагностического сообщения зависит от типа приложения, которое вызвало подпрограмму. Консольные приложения всегда получают сообщения через `stderr`. В приложении на основе Windows `assert` вызывает функцию Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) для создания окна сообщения для отображения сообщения вместе с кнопкой **ОК**. Когда пользователь нажимает **ОК**, программа немедленно завершается.  
  
 Когда приложение связывается с отладочной версией библиотеки среды выполнения, `assert` создает окно сообщения с тремя кнопками: **Прервать**, **Повторить** и **Пропустить**. Если пользователь нажимает кнопку **Прервать**, выполнение программы немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, вызывается отладчик, и пользователь может выполнить JIT\-отладку программы, если JIT\-отладка включена. Если пользователь нажимает кнопку **Пропустить**, `assert` продолжает нормальное выполнение: создает окно сообщения с кнопкой **ОК**. Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к неожиданному поведению.  
  
 Дополнительные сведения об отладке CRT см. в разделе [Методы отладки CRT](../Topic/CRT%20Debugging%20Techniques.md).  
  
 Функции `_assert` и `_wassert` являются внутренними функциями CRT. Они позволяют свести к минимуму объем кода, требуемый в объектных файлах для поддержки утверждений. Вызывать эти функции напрямую не рекомендуется.  
  
 Макрос `assert` включен и в окончательной, и в отладочной версиях библиотек среды выполнения C, если `NDEBUG` не определен. Если `NDEBUG` определен, макрос доступен, но его аргумент не вычисляется и макрос не оказывает никакого действия. Если макрос `assert` включен, он вызывает `_wassert` для своей реализации. Другие макросы утверждения, [\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), [\_ASSERTE](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) и [\_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), также доступны, но они вычисляют передаваемые им выражения только в том случае, если макрос [\_DEBUG](../Topic/_DEBUG.md) определен и они находятся в коде, связанном с отладочной версией библиотек среды выполнения C.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`assert`, `_wassert`|\<assert.h\>|  
  
 Сигнатура функции `_assert` не доступна в файле заголовка. Сигнатура функции `_wassert` доступна только в том случае, если макрос `NDEBUG` не определен.  
  
## Пример  
 В этой программе функция `analyze_string` использует макрос`assert` для проверки нескольких условий, связанных со строкой и длиной. Если какое\-либо из условий не выполняется, программа выводит сообщение, указывающее на причину сбоя.  
  
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
Analyzing string 'abc' Analyzing string '(null)' Assertion failed: string != NULL, file crt_assert.c, line 25  
```  
  
 После сбоя утверждения вы можете увидеть сообщение наподобие приведенного ниже \(точный текст зависит от версии операционной системы и библиотеки среды выполнения\).  
  
```Output  
Возникшая проблема привела к прекращению работы программы. Windows закроет эту программу, а если есть известный способ устранения проблемы, уведомит вас об этом.  
```  
  
 Если отладчик установлен, нажмите кнопку **Отладка**, чтобы запустить его, или кнопку **Закрыть программу**, чтобы выйти.  
  
## Эквивалент в .NET Framework  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## См. также  
 [Обработка ошибок](../../c-runtime-library/error-handling-crt.md)   
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [Макросы \_ASSERT, \_ASSERTE, \_ASSERT\_EXPR](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md)   
 [\_DEBUG](../Topic/_DEBUG.md)