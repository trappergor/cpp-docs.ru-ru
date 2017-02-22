---
title: "Обработка файлов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.files"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "файлы [C++], обработка"
  - "файлы [C++], обработка"
  - "файлы [C++], открытие"
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Обработка файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти подпрограммы предназначены для создания и удаления файлов, управления файлами, а также задания и проверки разрешений доступа к файлам.  
  
 В библиотеках времени выполнения C количество одновременно открытых файлов ограничено 512 файлами. Попытка открыть больше максимального количества дескрипторов файлов или файловых потоков приводит к сбою программы. Для изменения этого значения используйте функцию [\_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md).  
  
 Следующие подпрограммы работают с файлами, идентифицируемыми дескрипторами файлов.  
  
### Подпрограммы обработки файлов \(дескриптор файла\)  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|------------------|----------------|-------------------------------|  
|[\_chsize](../c-runtime-library/reference/chsize.md),[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|Изменяет размер файла|[System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx), [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)|  
|[\_filelength, \_filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|Получает длину файла|[System::IO::Stream::Length](https://msdn.microsoft.com/en-us/library/system.io.stream.length.aspx), [System::IO::FileStream::Length](https://msdn.microsoft.com/en-us/library/system.io.filestream.length.aspx)|  
|[\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|Получает сведения о состоянии файла по дескриптору|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Возвращает дескриптор файла операционной системы, связанный с существующими дескриптором файла среды выполнения C.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_isatty](../c-runtime-library/reference/isatty.md)|Проверяет символьное устройство|[System::IO::Stream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.filestream.canwrite.aspx), [System::IO::FileStream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.stream.canwrite.aspx)|  
|[\_locking](../Topic/_locking.md)|Блокирует области файла|[System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_setmode](../c-runtime-library/reference/setmode.md)|Устанавливает режим преобразования файлов|[System::IO::BinaryReader Class](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx), [System::IO::TextReader Class](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)|  
  
 Следующие подпрограммы работают с файлами, указанными с помощью пути или имени файла.  
  
### Подпрограммы обработки файлов \(путь или имя файла\)  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|------------------|----------------|-------------------------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md), [\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|Проверяет параметры разрешений файла|[Перечисление System::IO::FileAccess](https://msdn.microsoft.com/en-us/library/4z36sx0f.aspx)|  
|[\_chmod, \_wchmod](../c-runtime-library/reference/chmod-wchmod.md)|Изменяет параметры разрешений файла|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx), [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)|  
|[\_fullpath, \_wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|Расширяет относительный путь до абсолютного пути|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Объединяет компоненты пути в один полный путь|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Создает уникальное имя файла|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[remove, \_wremove](../c-runtime-library/reference/remove-wremove.md)|Удалить файл|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
|[rename, \_wrename](../c-runtime-library/reference/rename-wrename.md)|Переименовывает файл|[System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)|  
|[\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md), [\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Разбирает путь на компоненты|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_stat, \_stat64, \_stati64, \_wstat, \_wstat64, \_wstati64](../c-runtime-library/reference/stat-functions.md)|Получает сведения о состоянии файла по имени|[System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx), [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx), [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx), [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../Topic/_umask_s.md)|Задает маску разрешений по умолчанию для новых файлов, создаваемых программой|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)|  
|[\_unlink, \_wunlink](../Topic/_unlink,%20_wunlink.md)|Удалить файл|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
  
 Следующие подпрограммы открывают файлы.  
  
### Подпрограммы обработки файлов \(открытие файлов\)  
  
|Подпрограмма|Применение|Эквивалент .NET Framework|  
|------------------|----------------|-------------------------------|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Открывает файл и возвращает указатель на открытый файл.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Открывает поток в режиме совместного доступа к файлу и возвращает указатель на открытый файл.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|Открывает файл и возвращает дескриптор открытого файла.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Открывает файл в режиме совместного доступа и возвращает дескриптор открытого файла.||  
|[\_pipe](../c-runtime-library/reference/pipe.md)|Создает канал для чтения и записи.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Переназначает указатель файла.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
  
 Следующие функции предоставляют возможность изменить представление файла между структурой `FILE`, дескриптором файла и Win32\-дескриптором файла.  
  
||||  
|-|-|-|  
|[\_fdopen, \_wfdopen](../Topic/_fdopen,%20_wfdopen.md)|Связывает поток с файлом, который ранее был открыт для низкоуровневого ввода\-вывода, и возвращает указатель на открытый поток.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.filestream.aspx)|  
|[\_fileno](../Topic/_fileno.md)|Получает дескриптор файла, связанного с потоком.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|Возвращает дескриптор файла операционной системы, связанный с существующими дескриптором файла среды выполнения C.|Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
  
 Следующие функции Win32 также открывают файлы и каналы:  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Управление каталогами](../c-runtime-library/directory-control.md)   
 [Системные вызовы](../Topic/System%20Calls.md)