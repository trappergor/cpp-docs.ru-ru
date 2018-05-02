---
title: _CrtDbgReport, _CrtDbgReportW | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6857f264618065c6d88a5efa92ee5a19abbc0c67
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW

Создает отчет с сообщением об отладке и отправляет его в три возможных назначения (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtDbgReport(
   int reportType,
   const char *filename,
   int linenumber,
   const char *moduleName,
   const char *format [,
   argument] ...
);
int _CrtDbgReportW(
   int reportType,
   const wchar_t *filename,
   int linenumber,
   const wchar_t *moduleName,
   const wchar_t *format [,
   argument] ...
);
```

### <a name="parameters"></a>Параметры

*reportType функции*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**, и **_CRT_ASSERT**.

*filename*<br/>
Указатель на имя исходного файла, где возникло утверждение или отчет или **NULL**.

*linenumber*<br/>
Номер строки в исходном файле, где возникло утверждение или отчет или **NULL**.

*имя модуля*<br/>
Указатель на имя модуля (EXE или DLL), в котором возникло утверждение или отчет.

*format*<br/>
Указатель на строку управления форматом, которая использовалась для создания сообщения для пользователя.

*Аргумент*<br/>
Дополнительные подстановочные аргументы, используемые *формат*.

## <a name="return-value"></a>Возвращаемое значение

Для всех назначений отчетов **_CrtDbgReport** и **_CrtDbgReportW** возвращают -1, если возникает ошибка и 0, если ошибок не обнаружено. Однако если назначение отчета — окно с сообщением об отладке, а пользователь нажимает кнопку **Повторить**, эти функции возвращают значение 1. Если пользователь нажимает кнопку **Прервать** в окне с сообщением об отладке, эти функции немедленно прерываются и не возвращают значение.

[_RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) отладки вызовов макросов **_CrtDbgReport** отладке формирования отчетов. Версии этих макросов для расширенных символов в том числе в [_ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) и [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), используйте **_CrtDbgReportW** для Составление отчетов их отладки. Когда **_CrtDbgReport** или **_CrtDbgReportW** возвращает 1, эти макросы запускают отладчик, при условии, что время JIT-отладка включена.

## <a name="remarks"></a>Примечания

**_CrtDbgReport** и **_CrtDbgReportW** можно отправлять отчет об отладке в три разных назначения: файл отчета отладки, монитор отладки (отладчик Visual Studio) или окно сообщений отладчика. Две функции настройки, [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md), используются для задания назначения (назначений) для каждого типа отчета. Эти функции позволяют управлять назначением или назначениями для каждого типа отчета по отдельности. Например, можно указать, что *reportType функции* из **_CRT_WARN** только быть отправлены монитор отладки, а *reportType функции* из **_CRT_ASSERT** отправляться в окно сообщений отладки и файл пользовательских отчетов.

**_CrtDbgReportW** — это двухбайтовая версия **_CrtDbgReport**. Все выходные данные и параметры строки отображаются как строки расширенных символов; в противном случае — аналогично версии с однобайтовыми символами.

**_CrtDbgReport** и **_CrtDbgReportW** создают сообщение для пользователя для отчета об отладке, подставляя *аргумент*[**n**] аргументы в *формат* строку, с использованием того же правилами, определенными в **printf** или **wprintf** функции. Эти функции создают отчет об отладке и затем определить назначение или назначения, на основании текущих режимов отчета и файла, заданных для *reportType функции*. Когда отчет отправляется в окно сообщений отладки *filename*, **lineNumber**, и *moduleName* включаются сведения, отображаемые в окне.

В следующей таблице перечислены доступных вариантов для режима или режимов отчета и файла и соответствующее поведение функции **_CrtDbgReport** и **_CrtDbgReportW**. Эти параметры определяются как битовые флаги в функции \<crtdbg.h>.

|Режим отчета|Файл отчета|**_CrtDbgReport**, **_CrtDbgReportW** поведения|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Неприменимо|Записывает сообщение, используя [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API Windows.|
|**_CRTDBG_MODE_WNDW**|Неприменимо|Вызывает API Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) для создания окна сообщения, в котором будет отображаться сообщение вместе с кнопками **Прервать**, **Повторить** и **Пропустить**. Если пользователь щелкает **прервать**, **_CrtDbgReport** или **_CrtDbgReport** немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, функция возвращает значение 1. Если пользователь щелкает **Ignore**, выполнение продолжается и **_CrtDbgReport** и **_CrtDbgReportW** возвращают значение 0. Учтите, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к возникновению "неопределенного поведения".|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Записывает сообщение в предоставленный пользователем **ОБРАБОТКИ**, с помощью окон [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API и не проверяет допустимость дескриптора файла; приложение отвечает за открытие файла отчета и за передачу допустимого файла дескриптор.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Записывает сообщение в **stderr**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Записывает сообщение в **stdout**.|

Этот отчет можно отправить в одно, два или три назначения (или ни в одно из назначений). Дополнительные сведения о задании режима (режимов) и файла отчета см. в описании функций [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md). Дополнительные сведения об использовании макросов отладки и функций отчетов см. в разделе [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting).

Если приложению требуется большую гибкость, чем, обеспечиваемые **_CrtDbgReport** и **_CrtDbgReportW**, можно написать собственную функцию создания отчетов и подключить ее отчетов библиотеки времени выполнения C механизм, с помощью [_CrtSetReportHook](crtsetreporthook.md) функции.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h>|
|**_CrtDbgReportW**|\<crtdbg.h>|

**_CrtDbgReport** и **_CrtDbgReportW** являются расширениями Майкрософт. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_crtdbgreport.c
#include <crtdbg.h>

int main(int argc, char *argv[]) {
#ifdef _DEBUG
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);
#endif
}
```

Примеры изменения функций создания отчетов см. в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
