---
title: _get_tzname
ms.date: 10/22/2018
api_name:
- _get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: 9f86a4997c328e86597e3bad8a7f7a3a5f5f50b6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955627"
---
# <a name="_get_tzname"></a>_get_tzname

Возвращает представление названия часового пояса или названия часового пояса с переходом на летнее время (DST) в виде строки символов.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>Параметры

*претурнвалуе*<br/>
Длина строки *тимезоненаме* , включая знак завершения null.

*тимезоненаме*<br/>
Адрес символьной строки для представления имени часового пояса или летнего имени часового пояса (DST) в зависимости от *индекса*.

*сизеинбитес*<br/>
Размер строки символов *тимезоненаме* в байтах.

*номер*<br/>
Индекс, определяющий извлечение одного или двух названий часовых поясов.

|*номер*|Содержимое *тимезоненаме*|*тимезоненаме* значение по умолчанию|
|-|-|-|
|0|Название часового пояса|"PST"|
|1|Название часового пояса с переходом на летнее время|"PDT"|
|> 1 или < 0|в параметре **еинвал**|не изменено|

Если значения не изменяются явным образом во время выполнения, по умолчанию используются значения "PST" и "PDT" соответственно.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха, в противном случае — **значение типа** пересчета.

Если значение *тимезоненаме* равно **null**или *сизеинбитес* равно нулю или меньше нуля (но не оба), вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **еинвал**.

### <a name="error-conditions"></a>Условия ошибок

|*претурнвалуе*|*тимезоненаме*|*сизеинбитес*|*номер*|Возвращаемое значение|Содержимое *тимезоненаме*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|Длина названия часового пояса|**NULL**|0|0 или 1|0|не изменено|
|Длина названия часового пояса|Любое действие|> 0|0 или 1|0|Название часового пояса|
|не изменено|**NULL**|> 0|Любое действие|**EINVAL**|не изменено|
|не изменено|Любое действие|нуль|Любое действие|**EINVAL**|не изменено|
|не изменено|Любое действие|> 0|> 1|**EINVAL**|не изменено|

## <a name="remarks"></a>Примечания

Функция **_get_tzname** извлекает символьное представление текущего часового пояса или зимнего летнего имени часового пояса в адрес *тимезоненаме* в зависимости от значения индекса, а также размер строки в *претурнвалуе*. Если *тимезоненаме* имеет **значение NULL** , а *сизеинбитес* равен нулю, то в *претурнвалуе*возвращается размер строки, необходимой для хранения указанного часового пояса, и завершающее значение NULL в байтах. Значения индекса должны быть либо 0 для стандартного часового пояса, либо 1 для часового пояса "зимнее время". любые другие значения *индекса* имеют неопределенные результаты.

## <a name="example"></a>Пример

Этот пример вызывает **_get_tzname** , чтобы получить требуемый размер буфера для вывода текущего летнего имени часового пояса, выделяет буфер этого размера, вызывает **_get_tzname** еще раз для загрузки имени в буфер и выводит его на консоль.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>Вывод

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
