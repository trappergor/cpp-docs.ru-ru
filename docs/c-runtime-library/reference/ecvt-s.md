---
title: _ecvt_s
ms.date: 4/2/2020
api_name:
- _ecvt_s
- _o__ecvt_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e33840e772de770e0f05ae45d2c2d4bec7e09939
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348049"
---
# <a name="_ecvt_s"></a>_ecvt_s

Преобразует **двойное** число в строку. Это — версия функции [_ecvt](ecvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*_value*<br/>
Число, которое требуется преобразовать.

*_count*<br/>
Сохраненное число разрядов.

*_Dec*<br/>
Сохраненная позиция десятичной запятой.

*_Sign*<br/>
Знак преобразованного числа.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Возвращаемое значение|Значение в *буфере*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**Null**|any|any|any|any|any|**EINVAL**|Не изменено.|
|Не **NULL** (указывает на действительную память)|<=0|any|any|any|any|**EINVAL**|Не изменено.|
|any|any|any|any|**Null**|any|**EINVAL**|Не изменено.|
|any|any|any|any|any|**Null**|**EINVAL**|Не изменено.|

## <a name="security-issues"></a>Проблемы с безопасностью

**_ecvt_s** может привести к нарушению доступа, если *буфер* не указывает на действительную память и не является **NULL.**

## <a name="remarks"></a>Remarks

Функция **_ecvt_s** преобразует номер плавающей точки в строку символов. Параметром *_Value* является номер плавающей точки, который должен быть преобразован. Эта функция хранит до *подсчета* цифр *_Value* в виде строки и придатков нулевой символ (''0'). Если число цифр в *_Value* превышает *_Count,* цифра низкого порядка округляется. Если цифр меньше числа *подсчетов,* строка набивается нулями.

В строке сохраняются только цифры. Положение десятичной точки и знак *_Value* можно получить из *_Dec* и *_Sign* после звонка. *Параметр _Dec* указывает на величину, дающую положение десятичной точки по отношению к началу строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр *_Sign* указывает на целый ряд, указывающий на знак преобразованного числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.

Буфер длины **_CVTBUFSIZE** достаточен для любого значения плавающей точки.

Разница между **_ecvt_s** и **_fcvt_s** заключается в толковании *параметра _Count.* **_ecvt_s** интерпретирует *_Count* как общее число цифр в строке вывода, в то время как **_fcvt_s** интерпретирует *_Count* как число цифр после десятичной точки.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версия отладки этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательный заголовок|
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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
