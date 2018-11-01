---
title: Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR
ms.date: 11/04/2016
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
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
ms.openlocfilehash: d2d83c3afa8e22c1f75480fe2afefa8bf68be858
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598462"
---
# <a name="assert-asserte-assertexpr-macros"></a>Макросы _ASSERT, _ASSERTE, _ASSERT_EXPR

Вычисляет выражение и создания отчета об отладке, когда результат равен **False** (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>Параметры

*booleanExpression*<br/>
Скалярное выражение (включая выражения указателя), которое возвращает ненулевое значение (true) или 0 (false).

*message*<br/>
Расширенная строка, отображаемая в составе отчета.

## <a name="remarks"></a>Примечания

**_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** макросов использовать приложение с простой и четкий механизм для проверки предположений в процессе отладки. Пользоваться ими очень удобно: их не нужно заключать в операторы `#ifdef` , чтобы они не вызывались в окончательной сборке приложения. Эта гибкость обеспечивается использованием макроса [_DEBUG](../../c-runtime-library/debug.md) . **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** доступны только тогда, когда **_DEBUG** определяется во время компиляции. Когда **_DEBUG** — не определен, вызовы этих макросов удаляются во время предварительной обработки.

**_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** оценить их *booleanExpression* аргумент, и если результат равен **false**(0), выводят диагностическое сообщение и вызывают [_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) для создания отчета об отладке. **_ASSERT** макрос выводит простое диагностическое сообщение, **_ASSERTE** включает в сообщение, вызвавшее сбой выражение является строковым представлением и **_ASSERT_EXPR** включает в себя *сообщение* строку в диагностическое сообщение. Эти макросы не выполнять никаких действий при *booleanExpression* не равен нулю.

**_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** вызова **_CrtDbgReportW**, чего весь вывод в расширенных символов. **_ASSERTE** надлежащим образом выводит символы Юникода в *booleanExpression* и **_ASSERT_EXPR** выводит символы Юникода в *сообщение*.

Так как **_ASSERTE** макрос указывает вызвавшее сбой выражение и **_ASSERT_EXPR** позволяет указать сообщение, в созданном отчете, они дают пользователям возможность определить проблему без обращения к исходный код приложения. Однако недостаток состоит в том, что каждые *сообщение* напечатанная **_ASSERT_EXPR** и каждое выражение, вычисляемое **_ASSERTE** включается в выходные данные (в отладочной версии) файл приложения как строковая константа. Таким образом, если большое количество вызовов **_ASSERT_EXPR** или **_ASSERTE**, эти выражения могут значительно увеличить размер файла вывода.

Если иное не задано с помощью функций [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) , сообщения отображаются во всплывающем диалоговом окне, что эквивалентно следующей настройке:

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW** создает отчет об отладке и определяет его место или места назначения, в зависимости от текущего режима или режимов отчета и файла, определенного для **_CRT_ASSERT** тип отчета. По умолчанию ошибки и сбои проверочных утверждений направляются в окно сообщений отладчика. Функции [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md) используются для определения мест назначения для каждого типа отчета.

Если назначением является окно сообщений отладки и пользователь нажимает кнопку **повторите** кнопки **_CrtDbgReportW** возвращает 1, приводит к **_ASSERT_EXPR**, **_ ASSERT** и **_ASSERTE** макросы запускают отладчик при условии, что включена отладка just-in-time (JIT).

Дополнительные сведения о процессе формирования отчетов см. в описании функций [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) . Дополнительные сведения о разрешении сбоев проверочных утверждений и использовании этих макросов в качестве отладочных механизмов обработки ошибок см. в разделе [Использование макросов для проверки и создания отчетов](/visualstudio/debugger/macros-for-reporting).

В дополнение к **_ASSERT** макросы, [assert](assert-macro-assert-wassert.md) макрос может использоваться для проверки программной логики. Этот макрос доступен и в отладочной, и в окончательной версиях библиотек. Для формирования отчетов об отладке также предусмотрены отладочные макросы [_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) , однако они не вычисляют выражение. **_RPT** макросы создают простой отчет. **_RPTF** макросы: исходный файл и номер строки которой был вызван макрос отчета в созданном отчете. Доступны версии этих макросов расширенных символов (**_RPTW**, **_RPTFW**). Версии для расширенных символов идентичны версиям для узких символов, за исключением того, что для всех строковых параметров и вывода используются строки расширенных символов.

Несмотря на то что **_ASSERT_EXPR**, **_ASSERT** и **_ASSERTE** представляют собой макросы и доступны, включив \<crtdbg.h >, приложение должно быть скомпоновано с отладочной версия библиотеки времени выполнения C при **_DEBUG** определен, так как эти макросы вызывают другие функции времени выполнения.

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-----------|---------------------|
|**_ASSERT_EXPR**, **_ASSERT**, **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>Пример

В этой программе вызовов **_ASSERT** и **_ASSERTE** макросов для проверки условия `string1 == string2`. Если условие не выполняется, эти макросы выводят диагностическое сообщение. **_RPT** и **_RPTF** группа макросов также используется в этой программе в качестве альтернативы для **printf** функции.

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

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[Макрос assert, _assert, _wassert](assert-macro-assert-wassert.md)<br/>
[Макросы _RPT, _RPTF, _RPTW, _RPTFW](rpt-rptf-rptw-rptfw-macros.md)<br/>
