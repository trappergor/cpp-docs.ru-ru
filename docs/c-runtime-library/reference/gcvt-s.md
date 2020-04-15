---
title: _gcvt_s
ms.date: 4/2/2020
api_name:
- _gcvt_s
- _o__gcvt_s
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
- _gcvt_s
- gcvt_s
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
ms.openlocfilehash: 10d2b9af45b78a3f5ed673bde3d37894ccb00168
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345378"
---
# <a name="_gcvt_s"></a>_gcvt_s

Преобразует значение с плавающей запятой в строку. Это версия функции [_gcvt](gcvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _gcvt_s(
   char *buffer,
   size_t sizeInBytes,
   double value,
   int digits
);
template <size_t cchStr>
errno_t _gcvt_s(
   char (&buffer)[cchStr],
   double value,
   int digits
); // C++ only
```

### <a name="parameters"></a>Параметры

*Буфера*<br/>
Буфер для сохранения результата преобразования.

*размерInBytes*<br/>
Размер буфера.

*value*<br/>
Преобразуемое значение.

*digits*<br/>
Количество значащих цифр хранятся.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае отказа в связи с недопустимым параметром (см. недопустимые значения в следующей таблице) вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, возвращается код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Буфера*|*размерInBytes*|*value*|*digits*|Возвращает|Значение в *буфере*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**Null**|any|any|any|**EINVAL**|Не изменено.|
|Не **NULL** (указывает на действительную память)|нуль|any|any|**EINVAL**|Не изменено.|
|Не **NULL** (указывает на действительную память)|any|any|>= *размерInBytes*|**EINVAL**|Не изменено.|

**Проблемы с безопасностью**

**_gcvt_s** может создать нарушение доступа, если *буфер* не указывает на действительную память и не является **NULL.**

## <a name="remarks"></a>Remarks

Функция **_gcvt_s** преобразует *значение* плавающей точки в строку символа (которая включает десятичную точку и возможный знак байт) и хранит строку в *буфере.* *буфер* должен быть достаточно большим, чтобы вместить преобразованное значение плюс прекращающийся нулевой символ, который придатится автоматически. Буфер длины **_CVTBUFSIZE** достаточен для любого плавающего значения точки. Если используется размер буфера *цифр* No 1, функция не перезавершает конец буфера, поэтому не забудьте предоставить достаточный буфер для этой операции. **_gcvt_s** попытки производить *цифры* в десятичном формате. Если он не может, он производит *цифры* в экспоненциальном формате. Нули в конце могут исключаться из преобразования.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версия отладки этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h>|\<error.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_gcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char buf[_CVTBUFSIZE];
    int decimal;
    int sign;
    int err;

    err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);

    if (err != 0)
    {
        printf("_gcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 1.2
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt](gcvt.md)<br/>
