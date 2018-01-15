---
title: "_CrtSetReportFile | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
dev_langs: C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8487ca011355ad248bc38c2fc2d3265f0fad4995
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile
Применив функцию [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) для указания `_CRTDBG_MODE_FILE`, можно указать дескриптор файла для получения текста сообщения. `_CrtSetReportFile` также используется функциями [_CrtDbgReport, _CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) для указания места назначения текста (только в отладочной версии).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
_HFILE _CrtSetReportFile(   
   int reportType,  
   _HFILE reportFile   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `reportType`  
 Тип отчета: `_CRT_WARN`, `_CRT_ERROR` и `_CRT_ASSERT`.  
  
 `reportFile`  
 Новый файл отчета для `reportType`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 При успешном завершении функция `_CrtSetReportFile` возвращает предыдущий файл отчета, заданный для типа отчета, который определяется параметром `reportType`. Если в качестве параметра `reportType` передается недопустимое значение, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает значение `_CRTDBG_HFILE_ERROR`. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 `_CrtSetReportFile` используется с функцией [_CrtSetReportMode](../../c-runtime-library/reference/crtsetreportmode.md) для определения места (или мест) назначения для определенного типа отчетов, создаваемых `_CrtDbgReport`. Если `_CrtSetReportMode` вызывается для присвоения режиму создания отчетов `_CRTDBG_MODE_FILE` определенного типа отчетов, необходимо также вызвать `_CrtSetReportFile`, чтобы задать определенный файл или поток, которые нужно использовать в качестве места назначения. Если функция [_DEBUG](../../c-runtime-library/debug.md) не определена, вызовы `_CrtSetReportFile` удаляются на этапе предварительной обработки.  
  
 В следующей таблице приведен список доступных вариантов для параметра `reportFile` и соответствующее поведение функции `_CrtDbgReport`. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.  
  
 `file handle`  
 Дескриптор файла, который будет служить местом назначения для сообщений. Попытки проверить допустимость дескриптора не предпринимаются. Дескриптор файла необходимо открыть и закрыть. Пример:  
  
```  
HANDLE hLogFile;  
hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,   
   FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,   
   FILE_ATTRIBUTE_NORMAL, NULL);  
_CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_WARN, hLogFile);  
  
_RPT0(_CRT_WARN,"file message\n");  
CloseHandle(hLogFile);  
```  
  
 `_CRTDBG_FILE_STDERR`  
 Записывает в `stderr` сообщение, которое может быть переадресовано следующим образом:  
  
```  
freopen( "c:\\log2.txt", "w", stderr);  
_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);  
_CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);  
  
_RPT0(_CRT_ERROR,"1st message\n");  
```  
  
 `_CRTDBG_FILE_STDOUT`  
 Записывает в `stdout` сообщение, которые можно переадресовать.  
  
 `_CRTDBG_REPORT_FILE`  
 Возвращает текущий режим отчетов.  
  
 Файлом отчета, используемым каждым типом отчетов, можно управлять отдельно. Например, можно указать, что параметр `reportType` со значением `_CRT_ERROR` должен быть передан `stderr`, а параметр `reportType` со значением `_CRT_ASSERT` необходимо передать в пользовательский дескриптор файла или поток.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_CrtSetReportFile`|\<crtdbg.h>|\<errno.h>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
 **Библиотеки:** только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Процедуры отладки](../../c-runtime-library/debug-routines.md)