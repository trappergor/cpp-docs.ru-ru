---
title: _gcvt_s
ms.date: 04/05/2018
api_name:
- _gcvt_s
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
ms.openlocfilehash: da36641f6a3ba8dc1da0894aedbfa390d2e796ae
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625046"
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

*buffer*<br/>
Буфер для сохранения результата преобразования.

*сизеинбитес*<br/>
Размер буфера.

*value*<br/>
Преобразуемое значение.

*digits*<br/>
Количество значащих цифр хранятся.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае отказа в связи с недопустимым параметром (см. недопустимые значения в следующей таблице) вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, возвращается код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Условия ошибок

|*buffer*|*сизеинбитес*|*value*|*digits*|Назад|Значение в *буфере*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|Любое действие|Любое действие|Любое действие|**EINVAL**|Без изменений.|
|Not **null** (указывает на допустимый объем памяти)|нуль|Любое действие|Любое действие|**EINVAL**|Без изменений.|
|Not **null** (указывает на допустимый объем памяти)|Любое действие|Любое действие|>= *сизеинбитес*|**EINVAL**|Без изменений.|

**Проблемы безопасности**

**_gcvt_s** может создать нарушение прав доступа, если *буфер* не указывает на допустимый объем памяти и не равен **null**.

## <a name="remarks"></a>Заметки

Функция **_gcvt_s** преобразует *значение* с плавающей запятой в символьную строку (которая включает десятичную запятую и возможный байт знака) и сохраняет строку в *буфер*. *буфер* должен быть достаточно большим, чтобы разместить преобразованное значение, а также завершающий нуль-символ, который добавляется автоматически. Буфер длины **_CVTBUFSIZE** достаточно для любого значения с плавающей запятой. Если используется размер буфера *цифр* + 1, функция не перезаписывает конец буфера, поэтому не забудьте предоставить достаточный буфер для этой операции. **_gcvt_s** пытается выдавать цифры *цифр* в десятичном формате. Если это невозможно, в экспоненциальном формате создаются цифры *цифр* . Нули в конце могут исключаться из преобразования.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладочная версия этой функции сначала заполняет буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

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

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt](gcvt.md)<br/>
