---
title: _open_osfhandle | Документы Майкрософт
ms.custom: ''
ms.date: 12/12/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: beb8c074beeb47274fbae21ea293d0ea55f28d36
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

В случае успешного выполнения **_open_osfhandle** возвращает дескриптор файла времени выполнения C. В противном случае возвращается значение -1.

## <a name="remarks"></a>Примечания

**_Open_osfhandle** функция выделяет дескриптор файла времени выполнения C и связывает его с дескриптором файла операционной системы, заданные *osfhandle*. *Флаги* аргумент является целочисленным выражением, сформированным из одной или нескольких констант манифеста, определенных в Fcntl.h. Если два или более констант манифеста используются для формирования *флаги* аргумент, константы объединяются с помощью оператора побитового или ( **&#124;** ).

Fcntl.h определяет следующих констант манифеста:

**\_O\_APPEND** помещает указатель файла в конец файла перед каждой операцией записи.

**\_O\_: RDONLY** открывает файл только для чтения.

**\_O\_текст** открывает файл в текстовом (переведенном) режиме.

**\_O\_WTEXT** файл открывается в режиме Юникода (UTF-16 переведенные).

Чтобы закрыть файл, открытый с **_open_osfhandle**, вызовите [ \_закрыть](close.md). Базовый дескриптор файла операционной системы также закрывается с помощью вызова **_close**, поэтому нет необходимости вызывать функцию Win32 **CloseHandle** для исходного дескриптора. Если владельцем дескриптора файла **ФАЙЛ &#42;**  поток, затем вызвать [fclose](fclose-fcloseall.md) , **ФАЙЛ &#42;**  поток также закрывает дескриптор файла и базовый дескриптор. В этом случае не следует вызывать **_Закрыть** на дескриптор файла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
