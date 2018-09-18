---
title: Обработка файлов | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.files
dev_langs:
- C++
helpviewer_keywords:
- files [C++], handling
- files [C++], opening
- files [C++], manipulating
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a471d6743da0cf803de72a9f257dfa67bc0dcbd1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036362"
---
# <a name="file-handling"></a>Обработка файлов

Эти подпрограммы предназначены для создания и удаления файлов, управления файлами, а также задания и проверки разрешений доступа к файлам.

В библиотеках времени выполнения C количество одновременно открытых файлов ограничено 512 файлами. Попытка открыть больше максимального количества дескрипторов файлов или файловых потоков приводит к сбою программы. Для изменения этого значения используйте функцию [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) .

## <a name="file-handling-routines-file-descriptor"></a>Подпрограммы обработки файлов (дескриптор файла)

Эти подпрограммы работают с файлами, идентифицируемыми дескрипторами файлов.

|Подпрограмма|Для изменения этого значения используйте функцию|
|-------------|---------|
|[_chsize](../c-runtime-library/reference/chsize.md),[_chsize_s](../c-runtime-library/reference/chsize-s.md)|Изменяет размер файла|
|[_filelength, _filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Получает длину файла|
|[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Получает сведения о состоянии файла по дескриптору|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Возвращает дескриптор файла операционной системы, связанный с существующими дескриптором файла среды выполнения C.|
|[_isatty](../c-runtime-library/reference/isatty.md)|Проверяет символьное устройство|
|[_locking](../c-runtime-library/reference/locking.md)|Блокирует области файла|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы|
|[_setmode](../c-runtime-library/reference/setmode.md)|Устанавливает режим преобразования файлов|

## <a name="file-handling-routines-path-or-filename"></a>Подпрограммы обработки файлов (путь или имя файла)

Эти подпрограммы работают с файлами, указанными с помощью пути или имени файла.

|Подпрограмма|Использовать|
|-------------|---------|
|[_access, _waccess](../c-runtime-library/reference/access-waccess.md), [_access_s, _waccess_s](../c-runtime-library/reference/access-s-waccess-s.md)|Проверяет параметры разрешений файла|
|[_chmod, _wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Изменяет параметры разрешений файла|
|[_fullpath, _wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Расширяет относительный путь до абсолютного пути|
|[_makepath, _wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [_makepath_s, _wmakepath_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Объединяет компоненты пути в один полный путь|
|[_mktemp, _wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [_mktemp_s, _wmktemp_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Создает уникальное имя файла|
|[remove, _wremove](../c-runtime-library/reference/remove-wremove.md)|Удалить файл|
|[rename, _wrename](../c-runtime-library/reference/rename-wrename.md)|Переименовывает файл|
|[_splitpath, _wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [_splitpath_s, _wsplitpath_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Разбирает путь на компоненты|
|[_stat, _stat64, _stati64, _wstat, _wstat64, _wstati64](../c-runtime-library/reference/stat-functions.md)|Получает сведения о состоянии файла по имени|
|[_umask](../c-runtime-library/reference/umask.md), [_umask_s](../c-runtime-library/reference/umask-s.md)|Задает маску разрешений по умолчанию для новых файлов, создаваемых программой|
|[_unlink, _wunlink](../c-runtime-library/reference/unlink-wunlink.md)|Удалить файл|

## <a name="file-handling-routines-open-file"></a>Подпрограммы обработки файлов (открытие файлов)

Эти подпрограммы открывают файлы.

|Подпрограмма|Использовать|
|-------------|---------|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Открывает файл и возвращает указатель на открытый файл.|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Открывает поток в режиме совместного доступа к файлу и возвращает указатель на открытый файл.|
|[_open, _wopen](../c-runtime-library/reference/open-wopen.md)|Открывает файл и возвращает дескриптор открытого файла.|
|[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md), [_sopen_s, _wsopen_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Открывает файл в режиме совместного доступа и возвращает дескриптор открытого файла.|
|[_pipe](../c-runtime-library/reference/pipe.md)|Создает канал для чтения и записи.|
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Переназначает указатель файла.|

Эти подпрограммы предоставляют возможность изменить представление файла между структурой `FILE`, дескриптором файла и Win32-дескриптором файла.

|Подпрограмма|Использовать|
|-------------|---------|
|[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Связывает поток с файлом, который ранее был открыт для низкоуровневого ввода-вывода, и возвращает указатель на открытый поток.|
|[_fileno](../c-runtime-library/reference/fileno.md)|Получает дескриптор файла, связанного с потоком.|
|[_get_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Возвращает дескриптор файла операционной системы, связанный с существующими дескриптором файла среды выполнения C.|
|[_open_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы.|

Следующие функции Win32 также открывают файлы и каналы:

- [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea)

- [CreatePipe](https://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)

- [CreateNamedPipe](/windows/desktop/api/winbase/nf-winbase-createnamedpipea)

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Управление каталогами](../c-runtime-library/directory-control.md)<br/>
[Системные вызовы](../c-runtime-library/system-calls.md)<br/>
