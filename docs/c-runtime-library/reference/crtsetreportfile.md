---
title: _CrtSetReportFile | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4f2c7aeda689e3b941d460c05c0c5be5d69d69d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

После использования [_CrtSetReportMode](crtsetreportmode.md) для указания **_CRTDBG_MODE_FILE**, можно указать дескриптор файла для получения текста сообщения. **_CrtSetReportFile** также используется [_CrtDbgReport, _CrtDbgReportW](crtdbgreport-crtdbgreportw.md) для указания назначения текста (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>Параметры

*reportType функции*<br/>
Тип отчета: **_CRT_WARN**, **_CRT_ERROR**, и **_CRT_ASSERT**.

*reportFile*<br/>
Новый файл отчета для *reportType функции*.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_CrtSetReportFile** возвращает предыдущий файл отчета, определенный для типа отчета, указанного в *reportType функции*. Если передается недопустимое значение *reportType функции*, эта функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает **_CRTDBG_HFILE_ERROR**. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_CrtSetReportFile** используется с [_CrtSetReportMode](crtsetreportmode.md) для определения назначения (назначений) для определенного типа отчета созданные **_CrtDbgReport**. Когда **_CrtSetReportMode** был вызван для назначения **_CRTDBG_MODE_FILE** reporting режим для определенного типа отчета, **_CrtSetReportFile** следует вызвать для Определите конкретный файл или поток для использования в качестве назначения. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetReportFile** удаляются на этапе предварительной обработки.

В следующем списке приведены варианты для *reportFile* и соответствующее поведение функции **_CrtDbgReport**. Эти параметры задаются в виде битовых флагов в файле Crtdbg.h.

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

   Записывает сообщение в **stderr**, который может быть перенаправлен следующим образом:

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

Файлом отчета, используемым каждым типом отчетов, можно управлять отдельно. Например, можно указать, что *reportType функции* из **_CRT_ERROR** сообщает об **stderr**, пока *reportType функции* из **_CRT_ASSERT** отчеты для дескриптора файла, определяемых пользователем или поток.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
