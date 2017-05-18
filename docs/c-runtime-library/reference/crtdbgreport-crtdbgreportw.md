---
title: "_CrtDbgReport, _CrtDbgReportW | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: f197e4f6341508f05e566f45566f26a18be43bed
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport, _CrtDbgReportW
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
 Для всех назначений отчетов `_CrtDbgReport` и `_CrtDbgReportW` возвращают -1, если возникает ошибка и 0, если ошибок не обнаружено. Однако если назначение отчета — окно с сообщением об отладке, а пользователь нажимает кнопку **Повторить**, эти функции возвращают значение 1. Если пользователь нажимает кнопку **Прервать** в окне с сообщением об отладке, эти функции немедленно прерываются и не возвращают значение.  
  
 Макросы отладки [_RPT, _RPTF](../../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) вызывают `_CrtDbgReport` для создания отчетов об отладке. Версии этих макросов с расширенными символами, так же как и [_ASSERT&#91;E&#93;](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), `_RPTW n` и `_RPTFW n`, используют `_CrtDbgReportW` для создания отчетов об отладке. Если функция `_CrtDbgReport` или `_CrtDbgReportW` возвращает значение 1, эти макросы запускают отладчик при условии, что включена JIT-отладка.  
  
## <a name="remarks"></a>Примечания  
 `_CrtDbgReport` и `_CrtDbgReportW` могут отправлять отчет об отладке в три разных назначения: файл отчета об отладке, монитор отладки (отладчик [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]) или окно с сообщением об отладке. Две функции настройки, [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md), используются для задания назначения (назначений) для каждого типа отчета. Эти функции позволяют управлять назначением или назначениями для каждого типа отчета по отдельности. Например, можно указать, что `reportType` типа `_CRT_WARN` можно отправлять только в монитор отладки, а `reportType` типа `_CRT_ASSERT` — в окно с сообщением об отладке и пользовательский файл отчета.  
  
 `_CrtDbgReportW` — версия `_CrtDbgReport` с расширенными символами. Все выходные данные и параметры строки отображаются как строки расширенных символов; в противном случае — аналогично версии с однобайтовыми символами.  
  
 `_CrtDbgReport` и `_CrtDbgReportW` создают сообщение для пользователя для отчета об отладке, подставляя аргументы `argument`[`n`] в строку `format`, используя правила, определенные функциями `printf` и `wprintf`. Затем эти функции создают отчет об отладке и определяют назначение (назначения) в зависимости от текущих режимов отчета и файла, заданных для `reportType`. Когда отчет отправляется в окно с сообщением об отладке, `filename`, `lineNumber` и `moduleName` включаются в набор сведений, которые отображаются в окне.  
  
 В таблице ниже приведен список доступных вариантов для режима или режимов отчета и файла, а также поведение, которое является результатом функций `_CrtDbgReport` и `_CrtDbgReportW`. Эти параметры определяются как битовые флаги в функции \<crtdbg.h>.  
  
|Режим отчета|Файл отчета|Поведение `_CrtDbgReport`, `_CrtDbgReportW`|  
|-----------------|-----------------|------------------------------------------------|  
|`_CRTDBG_MODE_DEBUG`|Неприменимо|Записывает сообщение, используя [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API Windows.|  
|`_CRTDBG_MODE_WNDW`|Неприменимо|Вызывает API Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) для создания окна сообщения, в котором будет отображаться сообщение вместе с кнопками **Прервать**, **Повторить** и **Пропустить**. Если пользователь нажимает кнопку **Прервать**, функция `_CrtDbgReport` или `_CrtDbgReport` немедленно прерывается. Если пользователь нажимает кнопку **Повторить**, функция возвращает значение 1. Если пользователь нажимает кнопку **Пропустить**, выполнение продолжается и функции `_CrtDbgReport` и `_CrtDbgReportW` возвращают значение 0. Учтите, что нажатие кнопки **Пропустить** при наличии условия ошибки часто приводит к возникновению "неопределенного поведения".|  
|`_CRTDBG_MODE_FILE`|`__HFILE`|Записывает сообщение в предоставляемый пользователем `HANDLE` с использованием функции [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API Windows, не проверяя допустимость дескриптора файла; приложение отвечает за открытие файла отчета и передачу допустимого дескриптора файла.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDERR`|Записывает сообщение в `stderr`.|  
|`_CRTDBG_MODE_FILE`|`_CRTDBG_FILE_STDOUT`|Записывает сообщение в `stdout`.|  
  
 Этот отчет можно отправить в одно, два или три назначения (или ни в одно из назначений). Дополнительные сведения о задании режима (режимов) и файла отчета см. в описании функций [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) и [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md). Дополнительные сведения об использовании макросов отладки и функций отчетов см. в разделе [Макросы для создания отчетов](/visualstudio/debugger/macros-for-reporting).  
  
 Если приложению требуется больше гибкости, чем могут обеспечить функции `_CrtDbgReport` и `_CrtDbgReportW`, можно написать собственную функцию создания отчетов и подключить ее к механизму создания отчетов библиотеки времени выполнения языка C, используя функцию [_CrtSetReportHook](../../c-runtime-library/reference/crtsetreporthook.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_CrtDbgReport`|\<crtdbg.h>|  
|`_CrtDbgReportW`|\<crtdbg.h>|  
  
 `_CrtDbgReport` и `_CrtDbgReportW` являются расширениями Майкрософт. Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
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
  
 Примеры изменения функций создания отчетов см. в разделе [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)   
 [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md)   
 [_CrtSetReportFile](../../c-runtime-library/reference/crtsetreportfile.md)   
 [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [_DEBUG](../../c-runtime-library/debug.md)
