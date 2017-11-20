---
title: "Константы errno | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ENOEXEC
- ENOMEM
- E2BIG
- STRUNCATE
- ENOENT
- EMFILE
- EBADF
- EDEADLOCK
- EXDEV
- EILSEQ
- EINVAL
- EDOM
- EACCES
- ERANGE
- ENOSPC
- EAGAIN
- EEXIST
- ECHILD
dev_langs: C++
helpviewer_keywords:
- ENOEXEC constant
- EBADF constant
- EAGAIN constant
- EINVAL constant
- ENOENT constant
- errno constants
- E2BIG constant
- EMFILE constant
- EDEADLOCK constant
- ENOSPC constant
- EDOM constant
- ENOMEM constant
- EACCES constant
- EEXIST constant
- STRUNCATE constant
- ERANGE constant
- ECHILD constant
- EXDEV constant
- EILSEQ constant
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fdfb4477b4de30221a0e89db02cd45178b70db0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="errno-constants"></a>Константы errno
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <errno.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Значения **errno** — это константы, присваиваемые параметру [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) при возникновении различных ошибок.  
  
 ERRNO.H содержит определения для значений **errno**. Однако не все определения, приведенные в ERRNO.H, используются в 32-разрядных операционных системах Windows. Некоторые значения в ERRNO.H присутствуют для поддержки совместимости с операционными системами семейства UNIX.  
  
 Значения **errno** в 32-разрядной операционной системе Windows являются подмножеством значений **errno** в системах XENIX. Поэтому значение **errno** не всегда совпадает с фактическим кодом ошибки, который возвращает системный вызов из операционной системы Windows. Чтобы получить фактический код ошибки операционной системы, используйте переменную [_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), которая содержит это значение.  
  
 Поддерживаются следующие значения **errno**:  
  
 **ECHILD**  
 Нет порожденных процессов.  
  
 **EAGAIN**  
 Нет больше процессов. Попытка создать новый процесс завершилась ошибкой, поскольку больше нет слотов для процессов, недостаточно памяти или достигнут максимальный уровень вложенности.  
  
 **E2BIG**  
 Список аргументов слишком длинный.  
  
 **EACCES**  
 В разрешении отказано. Настройка разрешений файла не допускает указанный доступ. Эта ошибка означает, что предпринята попытка доступа к файлу (или, в некоторых случаях, к каталогу) способом, который несовместим с атрибутами файла.  
  
 Например, ошибка может возникнуть при попытке чтения из файла, который не был открыт, при попытке записи в файл, который предназначен только для чтения, или при попытке открыть не файл, а каталог. В операционной системе MS-DOS версии 3.0 и более поздних ошибка **EACCES** может также указывать на нарушение блокировки или общего доступа.  
  
 Ошибка может также возникать при попытке переименовать файл или каталог или при попытке удалить существующий каталог.  
  
 **EBADF**  
 Неверный номер файла. Возможны две причины: 1) Указанный дескриптор файла не является допустимым значением или не относится к открытому файлу. 2) Предпринята попытка записи в файл или устройство, которые были открыты только для чтения.  
  
 **EDEADLOCK**  
 Может произойти взаимоблокировка ресурсов. Аргумент математической функции не находится в домене этой функции.  
  
 **EDOM**  
 Математический аргумент.  
  
 **EEXIST**  
 Файлы существуют. Предпринята попытка создать файл, который уже существует. Например, в вызове функции **_open** указаны флаги **_O_CREAT** и **_O_EXCL**, но названный файл уже существует.  
  
 **EILSEQ**  
 Недопустимая последовательность байтов (например, в строке в многобайтовой кодировке (MBCS)).  
  
 **EINVAL**  
 Недопустимый аргумент. Для одного из аргументов функции указано недопустимое значение. Например, значение, заданное как начальное положение указателя файла (посредством вызова функции **fseek**), находится до начала файла.  
  
 **EMFILE**  
 Слишком много открытых файлов. Нет доступных дескрипторов файлов, поэтому невозможно открыть дополнительные файлы.  
  
 **ENOENT**  
 Отсутствует такой файл или каталог. Указанные файл или каталог не существуют или их не удалось найти. Это сообщение может выводиться, если указанный файл не существует или компонент пути не соответствует существующему каталогу.  
  
 **ENOEXEC**  
 Ошибка формата исполняемого файла. Предпринята попытка выполнения файла, который не является исполняемым или имеет недопустимый формат исполняемого файла.  
  
 **ENOMEM**  
 Недостаточно памяти. Недостаточно памяти для выполнения запрошенного оператора. Например, это сообщение может возникнуть, если не хватает памяти для выполнения дочернего процесса или не может быть удовлетворен запрос на выделение памяти в вызове **_getcwd**.  
  
 **ENOSPC**  
 На устройстве не осталось места. На устройстве нет больше доступного для записи места (например, при полном заполнении диска).  
  
 **ERANGE**  
 Результат слишком большой. Аргумент математической функции слишком велик, что приведет к частичной или полной потере значимости результата. Эта ошибка может также возникать в других функциях, если значение аргумента превышает ожидаемое значение (например, слишком длинный аргумент *buffer* при вызове **_getcwd**).  
  
 **EXDEV**  
 Ссылка между устройствами. Предпринята попытка переместить файл на другое устройство (с помощью функции **rename**).  
  
 **STRUNCATE**  
 Копирование или объединение строк привело к усечению строки. См. [_TRUNCATE](../c-runtime-library/truncate.md).  
  
 Для обеспечения совместимости с POSIX поддерживаются следующие значения. Они необходимы в системах, отличных от POSIX.  
  
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
  
## <a name="see-also"></a>См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)