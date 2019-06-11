---
title: _open_osfhandle
ms.date: 05/21/2019
apiname:
- _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 9e940844eb5e37755c10999feb294981afc8683a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821596"
---
# <a name="openosfhandle"></a>_open_osfhandle

Связывает дескриптор файла времени выполнения C с существующим дескриптором файла операционной системы.

## <a name="syntax"></a>Синтаксис

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Параметры

*osfhandle*<br/>
Дескриптор файла операционной системы.

*flags*<br/>
Разрешенные типы операций.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения функция **_open_osfhandle** возвращает дескриптор файла времени выполнения C. В противном случае она возвращает значение –1.

## <a name="remarks"></a>Примечания

**_Open_osfhandle** функция выделяет дескриптор файла времени выполнения C. Он связывает дескриптор этого файла с дескриптором файла операционной системы, заданные *osfhandle*. Чтобы компилятор не выдавал предупреждение, приведите аргумент *osfhandle* типа **HANDLE** к типу **intptr_t**. Аргумент *flags* представляет собой целочисленное выражение, сформированное на базе одной или нескольких констант манифеста, которые определяются в файле \<fcntl.h>. Можно использовать оператор побитового или ( **&#124;** ) для объединения двух или более констант манифеста, форму *флаги* аргумент.

Эти константы манифеста определены в файле \<fcntl.h>:

|||
|-|-|
| **\_O\_APPEND** | Помещает указатель файла в конец файла перед каждой операцией записи. |
| **\_O\_RDONLY** | Открывает файл только для чтения. |
| **\_O\_TEXT** | Открывает файл в текстовом режиме (с преобразованием). |
| **\_O\_WTEXT** | Открывает файл в режиме Юникода (с преобразованием UTF-16). |

Вызов **_open_osfhandle** передает право владения дескриптором файла Win32 дескриптору файла. Чтобы закрыть файл, открытый с помощью функции **_open_osfhandle**, вызовите функцию [\_close](close.md). Базовый дескриптор файла ОС также закрывается посредством вызова функции **_close**. Не вызывайте функцию Win32 **CloseHandle** применительно к исходному дескриптору. Если владельцем дескриптора файла **ФАЙЛ &#42;**  потока, а затем вызов [fclose](fclose-fcloseall.md) закрывает дескриптор файла и базовый дескриптор. В этом случае не вызывайте функцию **_close** для дескриптора файла или функцию **CloseHandle** для исходного дескриптора.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
