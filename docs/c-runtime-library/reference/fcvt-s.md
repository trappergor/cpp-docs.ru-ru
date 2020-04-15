---
title: _fcvt_s
ms.date: 4/2/2020
api_name:
- _fcvt_s
- _o__fcvt_s
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
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 80f02467e160e3196982c10576ad55f5487e5fc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347445"
---
# <a name="_fcvt_s"></a>_fcvt_s

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

*Буфера*<br/>
Предоставленный буфер, в который помещается результат преобразования.

*размерInBytes*<br/>
Размер буфера в байтах.

*value*<br/>
Число, которое требуется преобразовать.

*count*<br/>
Число разрядов после десятичной запятой.

*Декабря*<br/>
Указатель на сохраненную позицию десятичной запятой.

*Знак*<br/>
Указатель на сохраненный индикатор знака.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Буфера*|*размерInBytes*|значение|count|dec|подписывание|Возвращает|Значение в *буфере*|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**Null**|any|any|any|any|any|**EINVAL**|Не изменено.|
|Не **NULL** (указывает на действительную память)|<=0|any|any|any|any|**EINVAL**|Не изменено.|
|any|any|any|any|**Null**|any|**EINVAL**|Не изменено.|
|any|any|any|any|any|**Null**|**EINVAL**|Не изменено.|

## <a name="security-issues"></a>Проблемы с безопасностью

**_fcvt_s** может привести к нарушению доступа, если *буфер* не указывает на действительную память и не является **NULL.**

## <a name="remarks"></a>Remarks

Функция **_fcvt_s** преобразует номер плавающей точки в строку символов с нулевым завершением. Параметр *значения* — это номер плавающей точки, который должен быть преобразован. **_fcvt_s** хранит цифры *ценности* в виде строки и придатки нулевой символ (''0'). Параметр *подсчета* определяет количество цифр, которые будут храниться после десятичной точки. Избыточные цифры округлены для *подсчета* мест. Если количество *точного* количества меньше, строка набивается нулями.

В строке сохраняются только цифры. Положение десятичной точки и знак *значения* могут быть получены с *декабря* и *знака* после вызова. Параметр *dec* указывает на величину всей сделки; это значение рядом дает положение десятичной точки по отношению к началу строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. *Знак* параметра указывает на несколько с указанием знака *значения.* Целый ряд устанавливается до 0, если *значение* положительное и устанавливается на ненулевое число, если *значение* отрицательное.

Буфер длины **_CVTBUFSIZE** достаточен для любого плавающего значения точки.

Разница между **_ecvt_s** и **_fcvt_s** заключается в интерпретации параметра *подсчета.* **_ecvt_s** интерпретирует *считатьобщее* число цифр в строке вывода, а **_fcvt_s** интерпретирует *значение* как число цифр после десятичной точки.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версия отладки этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

**Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
