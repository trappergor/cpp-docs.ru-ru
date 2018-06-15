---
title: _open_osfhandle | Документы Майкрософт
ms.custom: ''
ms.date: 05/29/2018
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
ms.openlocfilehash: af3783420389dc008e39c818c39406f0b2af8af5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569840"
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

**_Open_osfhandle** функция выделяет дескриптор файла времени выполнения C и связывает его с дескриптором файла операционной системы, заданные *osfhandle*. Чтобы избежать предупреждения компилятора, приведите *osfhandle* аргумент из **ОБРАБОТКИ** для **intptr_t**. *Флаги* аргумент — это целочисленное выражение, образуемое из одной или нескольких констант манифеста, определенных в \<fcntl.h >. Если два или более констант манифеста используются для формирования *флаги* аргумент, константы объединяются с помощью оператора побитового или ( **&#124;** ).

Эти константы манифеста определены в \<fcntl.h >:

|||
|-|-|
**\_O\_APPEND**|Помещает указатель файла в конец файла перед каждой операцией записи.
**\_O\_: RDONLY**|Открывает файл только для чтения.
**\_O\_ТЕКСТА**|Открывает файл в текстовом режиме (с преобразованием).
**\_O\_WTEXT**|Открывает файл в режиме Юникода (с преобразованием UTF-16).

**_Open_osfhandle** вызов передает владение дескриптор файла Win32 дескриптор файла. Чтобы закрыть файл, открытый с **_open_osfhandle**, вызовите [ \_закрыть](close.md). Базовый дескриптор файла операционной системы также закрывается с помощью вызова **_close**, поэтому нет необходимости вызывать функцию Win32 **CloseHandle** для исходного дескриптора. Если владельцем дескриптора файла **ФАЙЛ &#42;**  поток, затем вызвать [fclose](fclose-fcloseall.md) , **ФАЙЛ &#42;**  поток также закрывает дескриптор файла и базовый дескриптор. В этом случае не следует вызывать **_Закрыть** на дескриптор файла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
