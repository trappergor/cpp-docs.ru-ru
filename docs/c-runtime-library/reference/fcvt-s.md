---
title: _fcvt_s
ms.date: 04/05/2018
apiname:
- _fcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 51ff3c675f1f53aee9beab629b17193164a2e7eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334870"
---
# <a name="fcvts"></a>_fcvt_s

Преобразует число с плавающей запятой в строку. Это версия функции [_fcvt](fcvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _fcvt_s(
   char* buffer,
   size_t sizeInBytes,
   double value,
   int count,
   int *dec,
   int *sign
);
template <size_t size>
errno_t _fcvt_s(
   char (&buffer)[size],
   double value,
   int count,
   int *dec,
   int *sign
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Предоставленный буфер, в который помещается результат преобразования.

*sizeInBytes*<br/>
Размер буфера в байтах.

*value*<br/>
Число, которое требуется преобразовать.

*count*<br/>
Число разрядов после десятичной запятой.

*dec*<br/>
Указатель на сохраненную позицию десятичной запятой.

*sign*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Условия ошибок

|*buffer*|*sizeInBytes*|value|count|dec|sign|Назад|Значение в *буфера*|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**NULL**|any|any|any|any|any|**EINVAL**|Без изменений.|
|Не **NULL** (указывает на допустимую память)|<=0|any|any|any|any|**EINVAL**|Без изменений.|
|any|any|any|any|**NULL**|any|**EINVAL**|Без изменений.|
|any|any|any|any|any|**NULL**|**EINVAL**|Без изменений.|

## <a name="security-issues"></a>Проблемы безопасности

**_fcvt_s** может генерировать событие нарушения доступа, если *буфера* не указывает на допустимый адрес в памяти и не **NULL**.

## <a name="remarks"></a>Примечания

**_Fcvt_s** функция преобразует число с плавающей запятой в строку символов с завершающим нулем. *Значение* параметром является номер с плавающей запятой для преобразования. **_fcvt_s** сохраняет цифры *значение* как строку и добавляет нуль-символ («\0»). *Число* указывает количество цифр, сохраняемых после десятичной запятой. Избыточные цифры округляются до *число* помещает. Если доступно менее *число* запятой, строка дополняется нулями.

В строке сохраняются только цифры. Положение десятичной запятой и знак *значение* можно получить из *dec* и *входа* после вызова метода. *Dec* параметр указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *входа* указывает на целое число, определяющее знак *значение*. Целое число имеет значение 0, если *значение* положительно и ненулевое значение, если задано значение *значение* является отрицательным.

Буфер длины **_CVTBUFSIZE** достаточно для любого с плавающей запятой.

Разница между **_ecvt_s** и **_fcvt_s** в интерпретацию *число* параметра. **_ecvt_s** интерпретирует *число* как общее число цифр в выходной строке, и **_fcvt_s** интерпретирует *число* как количество цифр после десятичной запятой.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочная версия этой функции сначала заполняет буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** Все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// fcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_fcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 120000
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
