---
title: "Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5dae684d922287c1301338ed3a59844ff6313ac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="assert-asserte-assertexpr-macros"></a>Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR
Вычисляют выражение и создают отчет об отладке, когда результат равен `False` (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_ASSERT_EXPR(  
   booleanExpression,  
   message  
);  
_ASSERT(   
   booleanExpression   
);  
_ASSERTE(   
   booleanExpression   
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `booleanExpression`  
 Скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (true) или 0 (false).  
  
 `message`  
 Расширенная строка, отображаемая в составе отчета.  
  
## <a name="remarks"></a>Примечания  
 Макросы `_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` представляют собой простой и четкий механизм, с помощью которого приложение может проверять условия во время процесса отладки. Пользоваться ими очень удобно: их не нужно заключать в операторы `#ifdef` , чтобы они не вызывались в окончательной сборке приложения. Эта гибкость обеспечивается использованием макроса [_DEBUG](../../c-runtime-library/debug.md) . Макросы`_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` доступны только тогда, когда макрос `_DEBUG` определен во время компиляции. Если флаг `_DEBUG` не определен, вызовы этих макросов удаляются во время предварительной обработки.  
  
 Макросы`_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` вычисляют свой аргумент `booleanExpression` argument и when the result is `false` (0), they print a diagnostic message и call [_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) для создания отчета об отладке. Макрос `_ASSERT` выводит простое диагностическое сообщение,  `_ASSERTE` включает в сообщение строковое представление выражения, которое привело к сбою, а `_ASSERT_EXPR` включает строку `message` в диагностическое сообщение. Эти макросы не выполняют никаких действий, если аргумент `booleanExpression` не равен нулю.  
  
 `_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` вызывают `_CrtDbgReportW`, благодаря чему выходные данные содержат только расширенные символы. `_ASSERTE` надлежащим образом выводит символы Юникода в `booleanExpression` , а `_ASSERT_EXPR` выводит символы Юникода в `message`.  
  
 Так как макрос `_ASSERTE` указывает вызвавшее сбой выражение, а `_ASSERT_EXPR` позволяет указать сообщение в создаваемом отчете, они позволяют определить проблему без обращения к исходному коду приложения. Однако недостаток состоит в том, что каждое `message` , выводимое `_ASSERT_EXPR` , и каждое выражение, вычисляемое `_ASSERTE` , включается в файл вывода (в отладочной версии) приложения как строковая константа. Поэтому при большом количестве вызовов `_ASSERT_EXPR` или `_ASSERTE`эти выражения могут значительно увеличить размер файла вывода.  
  
 Если иное не задано с помощью функций [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) , сообщения отображаются во всплывающем диалоговом окне, что эквивалентно следующей настройке:  
  
`_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);`  
  
 `_CrtDbgReportW` создает отчет об отладке и определяет его место или места назначения на основании текущего режима или режимов отчета и файла, определенного для типа отчета `_CRT_ASSERT` . По умолчанию ошибки и сбои проверочных утверждений направляются в окно сообщений отладчика. Функции [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.  
  
 Когда местом назначения является окно сообщений отладки и пользователь нажимает кнопку **Повторить** , `_CrtDbgReportW` возвращает 1, в результате чего макросы `_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` запускают отладчик при условии, что JIT-отладка включена.  
  
 Дополнительные сведения о процессе формирования отчетов см. в описании функций [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) . Дополнительные сведения о разрешении сбоев проверочных утверждений и использовании этих макросов в качестве отладочных механизмов обработки ошибок см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).  
  
 В дополнение к макросам `_ASSERT` использовать для проверки программной логики можно макрос [assert](../../c-runtime-library/reference/assert-macro-assert-wassert.md) . Этот макрос доступен и в отладочной, и в окончательной версиях библиотек. Для формирования отчетов об отладке также предусмотрены отладочные макросы [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) , однако они не вычисляют выражение. Макросы `_RPT` создают простой отчет. Макросы `_RPTF` включают в создаваемый отчет файл исходного кода и номер строки, на которой был вызван макрос отчета. Доступны версии этих макросов для расширенных символов (`_RPTWn`, `_RPTFWn`). Версии для расширенных символов идентичны версиям для узких символов, за исключением того, что для всех строковых параметров и вывода используются строки расширенных символов.  
  
 Хотя `_ASSERT_EXPR`, `_ASSERT` и `_ASSERTE` представляют собой макросы и, чтобы они были доступны, необходимо включить заголовок \<crtdbg.h>, приложение должно быть скомпоновано с отладочной версией библиотеки среды выполнения C, если определен макрос `_DEBUG`, так как эти макросы вызывают другие функции времени выполнения.  
  
## <a name="requirements"></a>Требования  
  
|Макрос|Обязательный заголовок|  
|-----------|---------------------|  
|`_ASSERT_EXPR`,                  `_ASSERT`, `_ASSERTE`|\<crtdbg.h>|  
  
## <a name="example"></a>Пример  
 В этой программе макросы `_ASSERT` и `_ASSERTE` вызываются для проверки условия `string1 == string2`. Если условие не выполняется, эти макросы выводят диагностическое сообщение. Группа макросов `_RPTn` и `_RPTFn` также используется в этой программе — в качестве альтернативы функции `printf` .  
  
```C  
// crt_ASSERT_macro.c  
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug  
//  
// This program uses the _ASSERT and _ASSERTE debugging macros.  
//  
  
#include <stdio.h>  
#include <string.h>  
#include <malloc.h>  
#include <crtdbg.h>  
  
int main()  
{  
   char *p1, *p2;  
  
   // The Reporting Mode and File must be specified  
   // before generating a debug report via an assert  
   // or report macro.  
   // This program sends all report types to STDOUT.  
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);  
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);  
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);  
  
   // Allocate and assign the pointer variables.  
   p1 = (char *)malloc(10);  
   strcpy_s(p1, 10, "I am p1");  
   p2 = (char *)malloc(10);  
   strcpy_s(p2, 10, "I am p2");  
  
   // Use the report macros as a debugging  
   // warning mechanism, similar to printf.  
   // Use the assert macros to check if the   
   // p1 and p2 variables are equivalent.  
   // If the expression fails, _ASSERTE will  
   // include a string representation of the  
   // failed expression in the report.  
   // _ASSERT does not include the  
   // expression in the generated report.  
   _RPT0(_CRT_WARN,  
       "Use the assert macros to evaluate the expression p1 == p2.\n");  
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);  
   _ASSERT(p1 == p2);  
  
   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",  
          p1, p2);  
   _ASSERTE(p1 == p2);  
  
   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);  
  
   free(p2);  
   free(p1);  
  
   return 0;  
}  
```  
  
```Output  
Use the assert macros to evaluate the expression p1 == p2.  
crt_ASSERT_macro.c(54) :   
 Will _ASSERT find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(55) : Assertion failed!  
crt_ASSERT_macro.c(58) :   
  
 Will _ASSERTE find 'I am p1' == 'I am p2' ?  
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2  
'I am p1' != 'I am p2'  
```  
  
## <a name="see-also"></a>См. также  
 [Подпрограммы отладки](../../c-runtime-library/debug-routines.md)   
 [Макрос assert, _assert, _wassert](../../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Макросы _RPT, _RPTF, _RPTW, _RPTFW](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)