---
title: "_CrtDbgReport, _CrtDbgReportW | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtDbgReport"
  - "_CrtDbgReportW"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtDbgReport"
  - "CrtDbgReportW"
  - "_CrtDbgReportW"
  - "_CrtDbgReport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "отчетность об отладке"
  - "_CrtDbgReport - функция"
  - "CrtDbgReport - функция"
  - "CrtDbgReportW - функция"
  - "_CrtDbgReportW - функция"
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtDbgReport, _CrtDbgReportW
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает отчет с сообщением об отладке и отправляет его в три возможных назначения (только отладочная версия).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `reportType`  
 Тип отчета: `_CRT_WARN`, `_CRT_ERROR` и `_CRT_ASSERT`.  
  
 `filename`  
 Указатель на имя исходного файла, в котором возникло утверждение или отчет, либо значение `NULL`.  
  
 `linenumber`  
 Номер строки в исходном файле, в которой возникло утверждение или отчет, либо значение `NULL`.  
  
 `moduleName`  
 Указатель на имя модуля (EXE или DLL), в котором возникло утверждение или отчет.  
  
 `format`  
 Указатель на строку управления форматом, которая использовалась для создания сообщения для пользователя.  
  
 `argument`  
 Дополнительные подстановочные аргументы, используемые `format`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Для всех назначений отчетов `_CrtDbgReport` и `_CrtDbgReportW` возвращают -1 при возникновении ошибки и 0, если ошибки отсутствуют. Тем не менее, если назначение отчета — это окно сообщения отладки и пользователь нажимает **повторите** кнопки, эти функции возвращают значение 1. Если пользователь нажимает кнопку **Прервать** кнопки в окне сообщений отладчика, эти функции немедленно прервать и не возвращать значение.  
  
  [_RPT, _RPTF](../Topic/_RPT,%20_RPTF,%20_RPTW,%20_RPTFW%20Macros.md) Отладка вызова макросы `_CrtDbgReport` для создания отчетов их отладке. Двухбайтовые версии этих макросов, а также [_ASSERT &#91; В &#93;](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md), `_RPTW``n` и `_RPTFW``n`, использовать `_CrtDbgReportW` для создания отчетов их отладке. Если функция `_CrtDbgReport` или `_CrtDbgReportW` возвращает значение 1, эти макросы запускают отладчик при условии, что включена JIT-отладка.  
  
## <a name="remarks"></a>Примечания  
 `_CrtDbgReport` и `_CrtDbgReportW` могут отправлять отчет об отладке в три разных назначения: файл отчета об отладке, монитор отладки (отладчик [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]) или окно с сообщением об отладке. Две функции настройки [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../Topic/_CrtSetReportFile.md), используемые для указания назначения (назначений) для каждого типа отчета. Эти функции позволяют управлять назначением или назначениями для каждого типа отчета по отдельности. Например, можно указать, что `reportType` типа `_CRT_WARN` можно отправлять только в монитор отладки, а `reportType` типа `_CRT_ASSERT` — в окно с сообщением об отладке и пользовательский файл отчета.  
  
 `_CrtDbgReportW` — версия `_CrtDbgReport` с расширенными символами. Все выходные данные и параметры строки отображаются как строки расширенных символов; в противном случае — аналогично версии с однобайтовыми символами.  
  
 `_CrtDbgReport` и `_CrtDbgReportW` создают сообщение для пользователя для отчета об отладке, подставляя аргументы `argument`[`n`] в строку `format`, используя правила, определенные функциями `printf` и `wprintf`. Затем эти функции создают отчет об отладке и определяют назначение (назначения) в зависимости от текущих режимов отчета и файла, заданных для `reportType`. Когда отчет отправляется в окно с сообщением об отладке, `filename`, `lineNumber` и `moduleName` включаются в набор сведений, которые отображаются в окне.  
  
 В таблице ниже приведен список доступных вариантов для режима или режимов отчета и файла, а также поведение, которое является результатом функций `_CrtDbgReport` и `_CrtDbgReportW`. Эти параметры определены как битовые флаги в \<crtdbg.h>.  
  
|Режим отчета|Файл отчета|Поведение `_CrtDbgReport`, `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Неприменимо|Записывает сообщение, используя Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API.|  
|`_CRTDBG_MODE_WNDW`|Неприменимо|Вызывает Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API для создания окна сообщения для отображения сообщения вместе с **Прервать**, **повторите**, и **Пропустить** кнопки. Если пользователь щелкает **Прервать**, `_CrtDbgReport` или `_CrtDbgReport` немедленно прерывается. Если пользователь щелкает **повторите**, функция возвращает значение 1. Если пользователь щелкает **Пропустить**, выполнение продолжается и `_CrtDbgReport` и `_CrtDbgReportW` возвращают значение 0. Обратите внимание, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к «неопределенного поведения».|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Записывает сообщение в предоставленный пользователем `HANDLE`, с помощью Windows [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API и не проверяет допустимость дескриптора файла; приложение отвечает за открытие файла отчета и передачу допустимого дескриптора файла.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Записывает сообщение в `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Записывает сообщение в `stdout`.|  
  
 Этот отчет можно отправить в одно, два или три назначения (или ни в одно из назначений). Дополнительные сведения об указании режима или режимов отчета и файла отчета см. в разделе [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../Topic/_CrtSetReportFile.md) функции. Дополнительные сведения об использовании макросов отладки и функций отчетов см. в разделе [макросы для создания отчетов](../Topic/Macros%20for%20Reporting.md).  
  
 Если приложению требуется больше гибкости, отсутствующие в `_CrtDbgReport` и `_CrtDbgReportW`, можно написать собственную функцию создания отчетов и подключить ее к механизму создания отчетов с помощью библиотеки во время выполнения C [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md) функции.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` и `_CrtDbgReportW` являются расширениями Майкрософт. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Отладочные версии [библиотеки времени выполнения C](../../c-runtime-library/crt-library-features.md) только.  
  
## <a name="example"></a>Пример  
  
```  
// crt_crtdbgreport.c  
#include <crtdbg.h>  
  
int main(int argc, char *argv[]) {  
#ifdef _DEBUG  
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);  
#endif  
}  
```  
  
 В разделе [crt_dbg2](http://msdn.microsoft.com/ru-ru/21e1346a-6a17-4f57-b275-c76813089167) Пример изменения функций создания отчетов.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
  
-   [System::Diagnostics::Debug::Write](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.write.aspx)  
  
-   [System::Diagnostics::Debug::WriteLine](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeline.aspx)  
  
-   [System::Diagnostics::Debug::WriteIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writeif.aspx)  
  
-   [System::Diagnostics::Debug::WriteLineIf](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.writelineif.aspx)  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../Topic/_CrtSetReportFile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../Topic/_DEBUG.md)