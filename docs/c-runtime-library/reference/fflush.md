---
title: fflush
ms.date: 4/2/2020
api_name:
- fflush
- _o_fflush
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
- fflush
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
ms.openlocfilehash: 401f715e99e6304f0726c8b9c96a71d9582dbc1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347166"
---
# <a name="fflush"></a>fflush

Записывает содержимое потока на диск.

## <a name="syntax"></a>Синтаксис

```C
int fflush(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fflush** возвращает 0, если буфер был успешно промыт. Кроме того, значение 0 также возвращается в случаях, когда указанный поток не имеет буфера или открыт только для чтения. Значение возврата **EOF** указывает на ошибку.

> [!NOTE]
> Если **fflush** возвращает **EOF,** данные могут быть потеряны из-за сбоя записи. При настройке обработчика критических ошибок безопаснее всего отключить буферизирование с функцией **setvbuf** или использовать низкоуровневые режимы ввоза/о, такие как **_open,** **_close**и **_write** вместо функций ввоза/ввоза потока.

## <a name="remarks"></a>Remarks

Функция **fflush** смывает *поток.* Если поток был открыт в режиме записи, а также если он был открыт в режиме обновления и последней была выполнена операция записи, содержимое буфера потока записывается в базовый файл или на базовое устройство, после чего буфер очищается. Если поток был открыт в режиме чтения, или если поток не имеет буфера, вызов **fflush** не имеет эффекта, и любой буфер сохраняется. Призыв к **fflush** сводит на нет эффект любого предварительного вызова **ungetc** для потока. После вызова поток остается открытым.

Если *поток* **NULL,** поведение такое же, как вызов **fflush** на каждом открытом потоке. Выполняется запись на диск всех потоков, открытых в режиме записи, а также всех потоков в режиме обновления, для которых последней была выполнена операция записи. Вызов не влияет на другие потоки.

Эти буферы обычно обслуживаются операционной системой, которая автоматически определяет оптимальное время записи данных на диск: при заполнении буфера, при закрытии потока или при нормальном завершении программы без закрытия потоков. Предусмотренная в библиотеке времени выполнения возможность фиксации на диск позволяет обеспечить запись критически важных данных непосредственно на диск, а не в буферы операционной системы. Эту возможность можно включить, не переписывая программу, а скомпоновав объектные файлы программы с файлом COMMODE.OBJ. В полученном исполняемом файле, призывы **к _flushall** записи содержимого всех буферов на диск. Только **_flushall** и **fflush** страдают от COMMODE.OBJ.

Дополнительные сведения об управлении возможностью фиксации на диск см. в разделах [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md), [fopen](fopen-wfopen.md) и [_fdopen](fdopen-wfdopen.md).

Функция блокирует вызывающий поток, поэтому она потокобезопасна. Для неблокирующей версии см. **_fflush_nolock**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fflush**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fflush.c
// Compile with: cl /W4 crt_fflush.c
// This sample gets a number from the user, then writes it to a file.
// It ensures the write isn't lost on crash by calling fflush.
#include <stdio.h>

int * crash_the_program = 0;

int main(void)
{
    FILE * my_file;
    errno_t err = fopen_s(&my_file, "myfile.txt", "w");
    if (my_file && !err)
    {
        printf("Write a number: ");

        int my_number = 0;
        scanf_s("%d", &my_number);

        fprintf(my_file, "User selected %d\n", my_number);

        // Write data to a file immediately instead of buffering.
        fflush(my_file);

        if (my_number == 5)
        {
            // Without using fflush, no data was written to the file
            // prior to the crash, so the data is lost.
            *crash_the_program = 5;
        }

        // Normally, fflush is not needed as closing the file will write the buffer.
        // Note that files are automatically closed and flushed during normal termination.
        fclose(my_file);
    }
    return 0;
}
```

```Input
5
```

```myfile.txt
User selected 5
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_flushall](flushall.md)<br/>
[setvbuf](setvbuf.md)<br/>
