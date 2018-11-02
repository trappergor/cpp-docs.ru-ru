---
title: _CrtDbgReport, _CrtDbgReportW
ms.date: 11/04/2016
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
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
ms.openlocfilehash: f12dafc62e302d90e5cffa04ee93e662b78295be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467799"
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

*reportType*<br/>
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

Для всех назначений отчетов **_CrtDbgReport** и **_CrtDbgReportW** возвращают значение -1, если произошла ошибка и 0, если ошибки не обнаружены. Однако если назначение отчета — окно с сообщением об отладке, а пользователь нажимает кнопку **Повторить**, эти функции возвращают значение 1. Если пользователь нажимает кнопку **Прервать** в окне с сообщением об отладке, эти функции немедленно прерываются и не возвращают значение.

[Макросы _RPT, _RPTF](rpt-rptf-rptw-rptfw-macros.md) отладка вызовов макросов **_CrtDbgReport** для создания отчетов их отладке. Двухбайтовые версии этих макросов в том числе в [макросы _ASSERT, _ASSERTE](assert-asserte-assert-expr-macros.md), [_RPTW](rpt-rptf-rptw-rptfw-macros.md) и [_RPTFW](rpt-rptf-rptw-rptfw-macros.md), использовать **_CrtDbgReportW** для Составление отчетов их отладки. Когда **_CrtDbgReport** или **_CrtDbgReportW** возвращает 1, эти макросы запускают отладчик, при условии, что включена отладка just-in-time (JIT).

## <a name="remarks"></a>Примечания

**_CrtDbgReport** и **_CrtDbgReportW** можно отправить отчет об отладке в три разных назначения: файл отчета отладки, монитор отладки (отладчик Visual Studio) или в окно сообщений отладчика. Две функции настройки, [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md), используются для задания назначения (назначений) для каждого типа отчета. Эти функции позволяют управлять назначением или назначениями для каждого типа отчета по отдельности. Например, можно указать, что *reportType* из **_CRT_WARN** только быть отправлены в монитор отладки, а *reportType* из **_CRT_ASSERT** отправляться в окно сообщений отладки и файл пользовательских отчетов.

**_CrtDbgReportW** — это двухбайтовая версия **_CrtDbgReport**. Все выходные данные и параметры строки отображаются как строки расширенных символов; в противном случае — аналогично версии с однобайтовыми символами.

**_CrtDbgReport** и **_CrtDbgReportW** создания пользовательского сообщения для отчета об отладке, подставляя *аргумент*[**n**] аргументы в *формат* string, используя те же правила, определяемые **printf** или **wprintf** функции. Эти функции создают отчет об отладке и затем определить место или места назначения, в зависимости от текущих режимов отчета и файла, заданных для *reportType*. Когда отчет отправляется в окно сообщений отладки, *filename*, **lineNumber**, и *moduleName* включаются сведения, отображаемые в окне.

В следующей таблице перечислены доступных вариантов для режима или режимов отчета и файла и соответствующее поведение функции **_CrtDbgReport** и **_CrtDbgReportW**. Эти параметры определяются как битовые флаги в функции \<crtdbg.h>.

|Режим отчета|Файл отчета|**_CrtDbgReport**, **_CrtDbgReportW** поведение|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|Неприменимо|Записывает сообщение, используя [OutputDebugString](https://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API Windows.|
|**_CRTDBG_MODE_WNDW**|Неприменимо|Вызывает API Windows [MessageBox](/windows/desktop/api/winuser/nf-winuser-messagebox) для создания окна сообщения, в котором будет отображаться сообщение вместе с кнопками **Прервать**, **Повторить** и **Пропустить**. Если пользователь щелкает **прервать**, **_CrtDbgReport** или **_CrtDbgReport** немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, функция возвращает значение 1. Если пользователь щелкает **пропустить**, выполнение продолжается и **_CrtDbgReport** и **_CrtDbgReportW** возвращают 0. Учтите, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к возникновению "неопределенного поведения".|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Записывает сообщение в предоставляемый пользователем **ОБРАБАТЫВАТЬ**, с помощью Windows [WriteFile](/windows/desktop/api/fileapi/nf-fileapi-writefile) API и не проверяет допустимость дескриптора файла; приложение отвечает за открытие файла отчета и передачу допустимого файла дескриптор.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|Записывает сообщение в **stderr**.|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|Записывает сообщение в **stdout**.|

Этот отчет можно отправить в одно, два или три назначения (или ни в одно из назначений). Дополнительные сведения о задании режима (режимов) и файла отчета см. в описании функций [_CrtSetReportMode](crtsetreportmode.md) и [_CrtSetReportFile](crtsetreportfile.md). Дополнительные сведения об использовании макросов отладки и функций отчетов см. в разделе [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting).

Если приложению требуется больше гибкости, чем поддерживаемые при **_CrtDbgReport** и **_CrtDbgReportW**, можно написать собственную функцию создания отчетов и подключить ее отчетов библиотеки времени выполнения C механизм, с помощью [_CrtSetReportHook](crtsetreporthook.md) функции.

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
