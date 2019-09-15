---
title: _CrtSetReportFile
ms.date: 11/04/2016
api_name:
- _CrtSetReportFile
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtSetReportFile
- _CrtSetReportFile
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: bf88bae40031f6e92d6f936ac8a50f85d6c4e36c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942284"
---
# <a name="_crtsetreportfile"></a>_CrtSetReportFile

После использования [_CrtSetReportMode](crtsetreportmode.md) для указания **_CRTDBG_MODE_FILE**можно указать описатель файла для получения текста сообщения. **_CrtSetReportFile** также используется [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) для указания места назначения текста (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**и **_CRT_ASSERT**.

*репортфиле*<br/>
Новый файл отчета для *reportType*.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_CrtSetReportFile** возвращает предыдущий файл отчета, определенный для типа отчета, указанного в *reportType*. Если для *reportType*передано недопустимое значение, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** задается значение, а функция возвращает **_CRTDBG_HFILE_ERROR**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_CrtSetReportFile** используется с функцией [_CrtSetReportMode](crtsetreportmode.md) для определения назначения или целевых объектов для конкретного типа отчета, созданного **_CrtDbgReport**. Когда **_CrtSetReportMode** вызывается для назначения режима отчетов **_CRTDBG_MODE_FILE** для определенного типа отчета, **_CrtSetReportFile** должен быть вызван для определения конкретного файла или потока, который будет использоваться в качестве назначения. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetReportFile** удаляются во время предварительной обработки.

В следующем списке приведены доступные варианты для *репортфиле* и результирующее поведение **_CrtDbgReport**. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.

- **описатель файла**

   Дескриптор файла, который будет служить местом назначения для сообщений. Попытки проверить допустимость дескриптора не предпринимаются. Дескриптор файла необходимо открыть и закрыть. Например:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   Записывает сообщение в **stderr**, которое можно перенаправить следующим образом:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Записывает сообщение в **stdout**, которое можно перенаправить.

- **_CRTDBG_REPORT_FILE**

   Возвращает текущий режим отчетов.

Файлом отчета, используемым каждым типом отчетов, можно управлять отдельно. Например, можно указать, что *reportType* **_CRT_ERROR** будет передан в **stderr**, а *reportType* **_CRT_ASSERT** — в определенный пользователем файловый обработчик или поток.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Консоль не поддерживается в приложениях универсальная платформа Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**и **stderr**, должны быть перенаправляться до того, как функции времени выполнения C смогут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Libraries** Только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
