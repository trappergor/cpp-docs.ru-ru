---
title: _CrtSetReportFile
ms.date: 11/04/2016
apiname:
- _CrtSetReportFile
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
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
ms.openlocfilehash: 32a560e09c47468daf48c185e23d6e289c6d1d9b
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343022"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

После использования [_CrtSetReportMode](crtsetreportmode.md) для указания **_CRTDBG_MODE_FILE**, можно указать дескриптор файла для получения текста сообщения. **_CrtSetReportFile** также используется процедурой [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) для указания места назначения текста (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Параметры

*reportType*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**, и **_CRT_ASSERT**.

*reportFile*<br/>
Новый файл отчета для *reportType*.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_CrtSetReportFile** возвращает предыдущий файл отчета, определенная для типа отчета, указанного в *reportType*. Если передается недопустимое значение *reportType*, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **_CRTDBG_HFILE_ERROR**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_CrtSetReportFile** используется с [_CrtSetReportMode](crtsetreportmode.md) функции для определения назначения (назначений) для определенного типа отчета созданные **_CrtDbgReport**. Когда **_CrtSetReportMode** был вызван для назначения **_CRTDBG_MODE_FILE** reporting режим для определенного типа отчета, **_CrtSetReportFile** затем должен быть вызван определения конкретного файла или потока, используемого в качестве места назначения. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtSetReportFile** удаляются во время предварительной обработки.

В следующем списке приведены доступных вариантов для *reportFile* и соответствующее поведение функции **_CrtDbgReport**. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.

- **Дескриптор файла**

   Дескриптор файла, который будет служить местом назначения для сообщений. Попытки проверить допустимость дескриптора не предпринимаются. Дескриптор файла необходимо открыть и закрыть. Пример:

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

   Записывает сообщение в **stderr**, которое может быть переадресовано следующим образом:

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   Записывает сообщение в **stdout**, которые можно перенаправить.

- **_CRTDBG_REPORT_FILE**

   Возвращает текущий режим отчетов.

Файлом отчета, используемым каждым типом отчетов, можно управлять отдельно. Например, можно указать, что *reportType* из **_CRT_ERROR** будут передаваться **stderr**, хотя *reportType* из **_CRT_ASSERT** будут передаваться в дескриптор пользовательский файл или поток.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** Отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) только.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
