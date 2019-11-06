---
title: _ecvt_s
ms.date: 04/05/2018
api_name:
- _ecvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: a37508c293ee72934a8580f822878f27031b864b
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624385"
---
# <a name="_ecvt_s"></a>_ecvt_s

Преобразует **Двойное** число в строку. Это — версия функции [_ecvt](ecvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*_Sign*<br/>
Знак преобразованного числа.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция **устанавливает** **Еинвал** и возвращает **еинвал**.

### <a name="error-conditions"></a>Условия ошибок

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Возвращаемое значение|Значение в *буфере*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|Любое действие|Любое действие|Любое действие|Любое действие|Любое действие|**EINVAL**|Без изменений.|
|Not **null** (указывает на допустимый объем памяти)|<=0|Любое действие|Любое действие|Любое действие|Любое действие|**EINVAL**|Без изменений.|
|Любое действие|Любое действие|Любое действие|Любое действие|**NULL**|Любое действие|**EINVAL**|Без изменений.|
|Любое действие|Любое действие|Любое действие|Любое действие|Любое действие|**NULL**|**EINVAL**|Без изменений.|

## <a name="security-issues"></a>Проблемы безопасности

**_ecvt_s** может вызвать нарушение прав доступа, если *буфер* не указывает на допустимый объем памяти и не равен **null**.

## <a name="remarks"></a>Заметки

Функция **_ecvt_s** преобразует число с плавающей запятой в символьную строку. Параметр *_Value* — это преобразуемое число с плавающей запятой. Эта функция сохраняет *количество* разрядов *в виде строки* и добавляет нуль-символ ("\ 0"). Если число цифр в *_Value* превышает *_Count*, младшие цифры округляются. Если число знаков меньше *числа* , строка дополняется нулями.

В строке сохраняются только цифры. Позиции десятичной запятой и знака *_Value* можно получить из *_Dec* и *_Sign* после вызова. Параметр *_Dec* указывает на целочисленное значение, определяющее позицию десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *_Sign* указывает на целое число, которое указывает знак преобразованного числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.

Буфер длины **_CVTBUFSIZE** достаточно для любого значения с плавающей запятой.

Разница между **_ecvt_s** и **_fcvt_s** заключается в интерпретации параметра *_Count* . **_ecvt_s** интерпретирует *_Count* как общее количество цифр в выходной строке, тогда как **_fcvt_s** интерпретирует *_Count* как число цифр после десятичной запятой.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладочная версия этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
