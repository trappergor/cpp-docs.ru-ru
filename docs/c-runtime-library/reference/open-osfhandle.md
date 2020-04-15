---
title: _open_osfhandle
ms.date: 4/2/2020
api_name:
- _open_osfhandle
- _o__open_osfhandle
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 16966bedd80dc90eaa89ee46e6b633a9cf7af74f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338547"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

Связывает дескриптор файлового времени выполнения C с существующей ручкой файла операционной системы.

## <a name="syntax"></a>Синтаксис

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Параметры

*osfhandle*<br/>
Ручка файла операционной системы.

*Флаги*<br/>
Разрешенные типы операций.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения функция **_open_osfhandle** возвращает дескриптор файла времени выполнения C. Иначе возвращается значение -1.

## <a name="remarks"></a>Remarks

Функция **_open_osfhandle** выделяет дескриптор файла времени выполнения C. Он связывает этот дескриптор файла с ручкой файла операционной системы, указанной *osfhandle.* Чтобы компилятор не выдавал предупреждение, приведите аргумент *osfhandle* типа **HANDLE** к типу **intptr_t**. Аргумент *flags* представляет собой целочисленное выражение, сформированное на базе одной или нескольких констант манифеста, которые определяются в файле \<fcntl.h>. Вы можете использовать оператора bitwise-OR **(&#124;),** чтобы объединить две или более манифест константы, чтобы сформировать аргумент *флагов.*

Эти константы манифеста определены в файле \<fcntl.h>:

|||
|-|-|
| **\_O\_APPEND** | Помещает указатель файла в конец файла перед каждой операцией записи. |
| **\_O\_RDONLY** | Открывает файл только для чтения. |
| **\_O\_ТЕКСТ** | Открывает файл в текстовом режиме (с преобразованием). |
| **\_O\_WTEXT** | Открывает файл в режиме Юникода (с преобразованием UTF-16). |

Вызов **_open_osfhandle** передает право владения дескриптором файла Win32 дескриптору файла. Чтобы закрыть файл, открытый с помощью функции **_open_osfhandle**, вызовите функцию [\_close](close.md). Базовый дескриптор файла ОС также закрывается посредством вызова функции **_close**. Не вызывайте функцию Win32 **CloseHandle** применительно к исходному дескриптору. Если дескриптор файла принадлежит потоку **FILE &#42;,** то вызов, чтобы [закрыть](fclose-fcloseall.md) закрывает как дескриптор файла, так и основную ручку. В этом случае не вызывайте функцию **_close** для дескриптора файла или функцию **CloseHandle** для исходного дескриптора.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
