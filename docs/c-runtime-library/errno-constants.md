---
title: "Константы errno | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ENOEXEC"
  - "ENOMEM"
  - "E2BIG"
  - "STRUNCATE"
  - "ENOENT"
  - "EMFILE"
  - "EBADF"
  - "EDEADLOCK"
  - "EXDEV"
  - "EILSEQ"
  - "EINVAL"
  - "EDOM"
  - "EACCES"
  - "ERANGE"
  - "ENOSPC"
  - "EAGAIN"
  - "EEXIST"
  - "ECHILD"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E2BIG - константа"
  - "EACCES - константа"
  - "EAGAIN - константа"
  - "EBADF - константа"
  - "ECHILD - константа"
  - "EDEADLOCK - константа"
  - "EDOM - константа"
  - "EEXIST - константа"
  - "EILSEQ - константа"
  - "EINVAL - константа"
  - "EMFILE - константа"
  - "ENOENT - константа"
  - "ENOEXEC - константа"
  - "ENOMEM - константа"
  - "ENOSPC - константа"
  - "ERANGE - константа"
  - "errno - константы"
  - "EXDEV - константа"
  - "STRUNCATE - константа"
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы errno
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <errno.h>  
```  
  
## Заметки  
 Значения **errno** \- это константы, присваиваемые [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) в случае различных условий ошибки.  
  
 ERRNO.H содержит определения значений **errno**.  Однако не все определения, приведенные в ERRNO.H, используются в 32\-разрядных операционных системах Windows.  Некоторые значения в ERRNO.H присутствуют для поддержки совместимости с операционными системами семейства UNIX.  
  
 Значения **errno** в 32\-разрядной операционной системе Windows являются подмножеством значений **errno** в системах XENIX.  Поэтому значение **errno** не обязательно совпадает с фактическим кодом ошибки, возвращаемым системным вызовом операционной системы Windows.  Чтобы получить фактический код ошибки операционной системы, используется переменная [\_doserrno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md), которая содержит это значение.  
  
 Поддерживаются следующие значения **errno**:  
  
 **ECHILD**  
 Нет порождённых процессов.  
  
 **EAGAIN**  
 Нет больше процессов.  Попытка создать новый процесс завершилась ошибкой, поскольку больше нет слотов для процессов, или недостаточно памяти, или достигнут максимальный уровень вложенности.  
  
 **E2BIG**  
 Слишком длинный список аргументов.  
  
 **EACCES**  
 Доступ запрещен.  Настройка разрешений файла не позволяет указанный доступ.  Эта ошибка означает, что предпринята попытка доступа к файлу \(в некоторых случаях к каталогу\) способом, который несовместим с атрибутами файла.  
  
 Например, ошибка может возникнуть при попытке чтения из файла, который не открыт, при попытке записи в файл, который предназначен только для чтения, или при попытке открыть не файл, а каталог.  В версиях операционной системы MS\-DOS версии 3.0 и более поздних версиях, **EACCES** может также указывать на нарушение блокировки или общего доступа.  
  
 Ошибка может также возникать при попытке переименовать файл или каталог или при попытке удалить существующий каталог.  
  
 **EBADF**  
 Неверный номер файла.  Возможны две причины: 1\) Указанный дескриптор файла не является допустимым значением или не относится к открытому файлу. 2\) Предпринята попытка записи в файл или устройство, которые были открыты только для чтения.  
  
 **EDEADLOCK**  
 Может произойти взаимоблокировка ресурса.  Аргумент математической функции не в домене этой функции.  
  
 **EDOM**  
 Математический аргумент.  
  
 **EEXIST**  
 Файлы существуют.  Предпринята попытка создать файл, который уже существует.  Например, флаги **\_O\_CREAT** и **\_O\_EXCL** указаны в вызове **\_open**, но названный файл уже существует.  
  
 **EILSEQ**  
 Недопустимая последовательность байтов \(например, в строке в кодировке MBCS\).  
  
 **EINVAL**  
 Недопустимый аргумент.  Для одного из аргументов функции было указано недопустимое значение.  Например, значение, заданное как начальное положение указателя файла \(посредством вызова **fseek**\) находится до начала файла.  
  
 **EMFILE**  
 Слишком много открытых файлов.  Больше нет доступных дескрипторов файлов, поэтому больше нельзя открывать файлы.  
  
 **ENOENT**  
 Нет такого файла или каталога.  Указанный файл или каталог не существуют, или их невозможно найти.  Это сообщение может произойти, если указанный файл не существует, или компонент пути не соответствует существующему каталогу.  
  
 **ENOEXEC**  
 Ошибка формата exec.  Предпринята попытка выполнения файл, который не является исполняемым или имеет недопустимый формат исполняемого файла.  
  
 **ENOMEM**  
 Недостаточно памяти.  Для предпринятого оператора недостаточно памяти.  Например, это сообщение может возникнуть, когда недостаточно памяти доступно для выполнения дочернего процесса, или если запрос на выделение в вызове **\_getcwd** не может быть удовлетворен.  
  
 **ENOSPC**  
 Нет места на выведенном устройстве.  На устройстве нет больше доступного для записи места \(например, при переполнении диска\).  
  
 **ERANGE**  
 Результат слишком велик.  Аргумент математической функции слишком велик, что приведет к частичной или полной потери значимости в результате.  Эта ошибка может также возникать в других функциях, если аргумент больше, чем ожидалось \(например, когда аргумент *buffer* в **\_getcwd** длиннее, чем ожидалось\).  
  
 **EXDEV**  
 Ссылка из другого устройства.  Предпринята попытка переместить файл на другое устройство \(с помощью функции **rename**\).  
  
 **STRUNCATE**  
 Копирование или объединение строк привело к усечению строки.  См. раздел [\_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Для обеспечения совместимости с POSIX поддерживаются следующие значения.  Эти значения необходимы в не POSIX системах.  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)