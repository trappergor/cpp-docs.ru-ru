---
title: _ecvt_s
ms.date: 04/05/2018
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: 0123c618eb5ba614bd8e5b5b3f1f4b0aff539c4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288261"
---
# <a name="ecvts"></a>_ecvt_s

Преобразует **двойные** чисел в строку. Это — версия функции [_ecvt](ecvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>Параметры

*_Buffer*<br/>
Заполняется указателем на строку разрядов, результат преобразования.

*_SizeInBytes*<br/>
Размер буфера в байтах.

*_Value*<br/>
Число, которое требуется преобразовать.

*_Count*<br/>
Сохраненное число разрядов.

*_Dec*<br/>
Сохраненная позиция десятичной запятой.

*_Подписать*<br/>
Знак преобразованного числа.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Условия ошибок

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Возвращаемое значение|Значение в *буфера*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|any|any|any|any|any|**EINVAL**|Без изменений.|
|Не **NULL** (указывает на допустимую память)|<=0|any|any|any|any|**EINVAL**|Без изменений.|
|any|any|any|any|**NULL**|any|**EINVAL**|Без изменений.|
|any|any|any|any|any|**NULL**|**EINVAL**|Без изменений.|

## <a name="security-issues"></a>Проблемы безопасности

**_ecvt_s** может генерировать событие нарушения доступа, если *буфера* не указывает на допустимый адрес в памяти и не **NULL**.

## <a name="remarks"></a>Примечания

**_Ecvt_s** функция преобразует число с плавающей запятой в строку символов. *_Значение* параметром является номер с плавающей запятой для преобразования. Эта функция сохраняет до *число* цифры *_значение* как строку и добавляет нуль-символ («\0»). Если количество цифр в *_значение* превышает *_Count*, младший разряд округляется. Если доступно менее *число* цифр, строка дополняется нулями.

В строке сохраняются только цифры. Положение десятичной запятой и знак *_значение* можно получить из *_Dec* и *_подписать* после вызова метода. *_Dec* параметр указывает на целочисленное значение, отражающее положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. *_Подписать* указывает параметр в целое число, указывающее знак преобразованного числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.

Буфер длины **_CVTBUFSIZE** достаточно для любого значения с плавающей запятой.

Разница между **_ecvt_s** и **_fcvt_s** в интерпретацию *_Count* параметра. **_ecvt_s** интерпретирует *_Count* как общее число цифр в выходной строке, тогда как **_fcvt_s** интерпретирует *_Count* как количество цифр после десятичной запятой.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочная версия этой функции сначала заполняет буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
