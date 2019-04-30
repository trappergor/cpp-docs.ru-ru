---
title: _heapwalk
ms.date: 11/04/2016
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
ms.openlocfilehash: cc2a49d9032746cc6c82c9dc401fc96baabbe2e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331692"
---
# <a name="heapwalk"></a>_heapwalk

Выполняет обход кучи и возвращает сведения о следующей записи.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows, за исключением отладочных сборок. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Параметры

*entryinfo*<br/>
Буфер, который будет содержать данные кучи.

## <a name="return-value"></a>Возвращаемое значение

**_heapwalk** возвращает одно из следующих целочисленных констант манифеста определенных в файле Malloc.h.

|Возвращаемое значение|Значение|
|-|-|
|**_HEAPBADBEGIN**| Начальные сведения о заголовке недопустимы или не найдены.|
|**_HEAPBADNODE**| Куча повреждена или обнаружен плохой узел.|
|**_HEAPBADPTR**| **_Pentry** поле **_HEAPINFO** структура не содержит допустимого указателя на кучу или *entryinfo* является пустым указателем.|
|**_HEAPEND**| Успешно достигнут конец кучи.|
|**_HEAPEMPTY**| Куча еще не инициализирована.|
|**_HEAPOK**| Пока; без ошибок *entryinfo* обновляется с учетом сведений о следующей записи кучи.|

Кроме того, если возникает ошибка **_heapwalk** задает **errno** для **ENOSYS**.

## <a name="remarks"></a>Примечания

**_Heapwalk** функция помогает при отладке в программах проблем, связанных с кучей. Функция выполняет обход кучи, проходя по одной записи на один вызов и возвращает указатель на структуру типа **_HEAPINFO** , содержащий сведения о следующей записи кучи. **_HEAPINFO** типы, определенные в файле Malloc.h, содержит следующие элементы.

|Поле|Значение|
|-|-|
|`int *_pentry`|Указатель записи кучи.|
|`size_t _size`|Размер записи кучи.|
|`int _useflag`|Флаг, указывающий, используется ли запись кучи.|

Вызов **_heapwalk** , возвращающий **_HEAPOK** сохраняет размер записи в **_размер** поля и наборы **_useflag** поле **_FREEENTRY** или **_USEDENTRY** (оба являются константы, определенные в файле Malloc.h). Для получения этих сведений о первой записи в куче следует передать **_heapwalk** указатель на **_HEAPINFO** структуры, **_pentry** член является **NULL** . Если операционная система не поддерживает **_heapwalk**(например, Windows 98), функция возвращает **_HEAPEND** и задает **errno** для **ENOSYS**.

Эта функция проверяет свои параметры. Если *entryinfo* является пустым указателем, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **_HEAPBADPTR**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
