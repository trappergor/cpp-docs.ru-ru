---
title: errno, _doserrno, _sys_errlist, and _sys_nerr
ms.date: 11/04/2016
apiname:
- _errno
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _sys_errlist
- errno
- _sys_nerr
- _doserrno
helpviewer_keywords:
- error codes, printing
- sys_errlist global variable
- doserrno global variable
- errno global variable
- _doserrno global variable
- _sys_errlist global variable
- _sys_nerr global variable
- sys_nerr global variable
ms.assetid: adbec641-6d91-4e19-8398-9a34046bd369
ms.openlocfilehash: 50b44c659aac66dbaddad711cceef635f277d2c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487732"
---
# <a name="errno-doserrno-syserrlist-and-sysnerr"></a>errno, _doserrno, _sys_errlist, and _sys_nerr

Глобальные макросы, которые содержат коды ошибок, задаваемые во время выполнения программы, и строковые эквиваленты кодов ошибок для отображения на экране.

## <a name="syntax"></a>Синтаксис

```
#define errno   (*_errno())
#define _doserrno   (*__doserrno())
#define _sys_errlist (__sys_errlist())
#define _sys_nerr (*__sys_nerr())
```

## <a name="remarks"></a>Примечания

Как для `errno`, так и для `_doserrno` средой выполнения во время запуска программы задается значение 0. `errno` возникает при ошибке в вызове системного уровня. Поскольку `errno` хранит значение для последнего вызова, задавшего его, это значение может быть изменено успешными вызовами. Вызовы библиотеки времени выполнения, задающие `errno` при ошибке, не сбрасывают `errno` при успешном завершении. Всегда сбрасывайте `errno` путем вызова функции `_set_errno(0)` сразу после вызова, который мог задать значение этой переменной, и проверяйте его сразу после вызова.

При возникновении ошибки `errno` необязательно присваивается то же значение, что и код ошибки, возвращаемый системным вызовом. Для операций ввода-вывода `_doserrno` хранит коды ошибок операционной системы, эквивалентные кодам `errno`. Для большинства операций, не относящихся к вводу-выводу, значение `_doserrno` не задано.

Каждое значение `errno` связано с сообщением об ошибке в `_sys_errlist`, которое можно напечатать, используя одну из функций [perror](../c-runtime-library/reference/perror-wperror.md), или сохранить в строке, используя одну из функций [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) или [strerror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md). `perror` и `strerror` используют массив `_sys_errlist` и `_sys_nerr` (количество элементов в `_sys_errlist`) для обработки сведений об ошибке. Прямой доступ к `_sys_errlist` и `_sys_nerr` является нерекомендуемым по причинам безопасности кода. Рекомендуется использовать более безопасные функциональные версии вместо глобальных макросов, как показано ниже.

|Глобальный макрос|Функциональные эквиваленты|
|------------------|----------------------------|
|`_doserrno`|[_get_doserrno](../c-runtime-library/reference/get-doserrno.md), [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)|
|`errno`|[_get_errno](../c-runtime-library/reference/get-errno.md), [_set_errno](../c-runtime-library/reference/set-errno.md)|
|`_sys_errlist`, `_sys_nerr`|[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|

Математические подпрограммы библиотек задают значение `errno` путем вызова [_matherr](../c-runtime-library/reference/matherr.md). Для обработки математических ошибок иным образом напишите собственную процедуру в соответствии с базовым описанием `_matherr` и назовите ее `_matherr`.

Все значения `errno` в следующей таблице являются предопределенными константами в \<errno.h> и совместимы с UNIX. Только `ERANGE`, `EILSEQ` и `EDOM` определены в стандарте ISO C99.

|Константа|Системное сообщение об ошибке|Значение|
|--------------|--------------------------|-----------|
|`EPERM`|Операция не разрешена|1|
|`ENOENT`|Отсутствует такой файл или каталог|2|
|`ESRCH`|Отсутствует такой процесс|3|
|`EINTR`|Прерванная функция|4|
|`EIO`|Ошибка ввода-вывода|5|
|`ENXIO`|Отсутствует такое устройство или адрес|6|
|`E2BIG`|Список аргументов слишком длинный|7|
|`ENOEXEC`|Ошибка формата exec|8|
|`EBADF`|Неверный номер файла|9|
|`ECHILD`|Нет порожденных процессов|10|
|`EAGAIN`|Больше процессов нет или недостаточно памяти, или достигнут максимальный уровень вложенности|11|
|`ENOMEM`|Недостаточно памяти|12|
|`EACCES`|В разрешении отказано|13|
|`EFAULT`|Неверный адрес|14|
|`EBUSY`|Устройство или ресурс заняты|16|
|`EEXIST`|Файл существует|17|
|`EXDEV`|Ссылка другого устройства|18|
|`ENODEV`|Нет такого устройства|19|
|`ENOTDIR`|Не является каталогом|20|
|`EISDIR`|Является каталогом|21|
|`EINVAL`|Недопустимый аргумент|22|
|`ENFILE`|Слишком много файлов открыто в системе|23|
|`EMFILE`|Слишком много открытых файлов|24|
|`ENOTTY`|Неподходящая операция управления вводом-выводом|25|
|`EFBIG`|Файл слишком велик|27|
|`ENOSPC`|На устройстве не осталось места|28|
|`ESPIPE`|Недопустимый поиск|29|
|`EROFS`|Файловая система доступна только для чтения|30|
|`EMLINK`|Слишком много ссылок|31|
|`EPIPE`|Канал нарушен|32|
|`EDOM`|Математический аргумент|33|
|`ERANGE`|Результат слишком большой|34|
|`EDEADLK`|Может произойти взаимоблокировка ресурсов|36|
|`EDEADLOCK`|Аналогично EDEADLK для обеспечения совместимости с предыдущими версиями Microsoft C|36|
|`ENAMETOOLONG`|Слишком длинное имя файла|38|
|`ENOLCK`|Нет доступных блокировок|39|
|`ENOSYS`|Функция не поддерживается|40|
|`ENOTEMPTY`|Каталог не пуст|41|
|`EILSEQ`|Недопустимая последовательность байтов|42|
|`STRUNCATE`|Строка была обрезана|80|

## <a name="requirements"></a>Требования

|Глобальный макрос|Обязательный заголовок|Необязательный заголовок|
|------------------|---------------------|---------------------|
|`errno`|\<errno.h> or \<stdlib.h>, \<cerrno> или \<cstdlib> (C++)||
|`_doserrno`, `_sys_errlist`, `_sys_nerr`|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

Макросы `_doserrno`, `_sys_errlist` и `_sys_nerr` являются расширениями Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Глобальные переменные](../c-runtime-library/global-variables.md)<br/>
[Константы errno](../c-runtime-library/errno-constants.md)<br/>
[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)<br/>
[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)<br/>
[_get_doserrno](../c-runtime-library/reference/get-doserrno.md)<br/>
[_set_doserrno](../c-runtime-library/reference/set-doserrno.md)<br/>
[_get_errno](../c-runtime-library/reference/get-errno.md)<br/>
[_set_errno](../c-runtime-library/reference/set-errno.md)