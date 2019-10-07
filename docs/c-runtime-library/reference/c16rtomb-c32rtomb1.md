---
title: c16rtomb, c32rtomb
ms.date: 01/22/2018
api_name:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
ms.openlocfilehash: a16effe48442ccbb5144b57ead2fb15c908fe898
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943429"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Преобразует расширенный символ в кодировке UTF-16 или UTF-32 в многобайтовый массив в текущем языковом стандарте.

## <a name="syntax"></a>Синтаксис

```C
size_t c16rtomb(
    char *mbchar,
    char16_t wchar,
    mbstate_t *state
);
size_t c32rtomb(
    char *mbchar,
    char32_t wchar,
    mbstate_t *state
);
```

### <a name="parameters"></a>Параметры

*мбчар*<br/>
Указатель на массив для хранения преобразованного многобайтового символа.

*wchar*<br/>
Расширенный символ для преобразования.

*state*<br/>
Указатель на объект **mbstate_t** .

## <a name="return-value"></a>Возвращаемое значение

Число байтов, хранящихся в объекте массива *мбчар*, включая любые последовательности сдвигов. Если параметр *WCHAR* не является допустимым расширенным символом, возвращается значение (**size_t**) (-1), параметру « **еилсек** *» присваивается* **значение «не** указано».

## <a name="remarks"></a>Примечания

Функция **c16rtomb** преобразует символ *WCHAR* в кодировке UTF-16 в эквивалентную многобайтовую последовательность символов в текущем языковом стандарте. Если *мбчар* не является пустым указателем, функция сохраняет преобразованную последовательность в объекте массива, на который указывает *мбчар*. До **MB_CUR_MAX** байт хранятся в *мбчар*, а *State* — в полученном состоянии многобайтовых сдвигов.    Если параметр *WCHAR* является расширенным символом NULL, то последовательность, необходимая для восстановления первоначального состояния сдвига, сохраняется, при необходимости, за которой следует символ null, а *State* — начальное состояние преобразования. Функция **c32rtomb** идентична, но ПРЕОБРАЗУЕТ символ UTF-32.

Если *мбчар* является пустым указателем, поведение эквивалентно вызову функции, которая заменяет внутренний буфер для *мбчар* и широкий символ NULL для *WCHAR*.

Объект состояния преобразования *состояния* позволяет выполнять последующие вызовы этой функции и других перезапускаемых функций, которые сохраняют состояние сдвига многобайтовых выходных символов. Результаты не определены при использовании перезапускаемых и незапускаемых функций, а также при осуществлении вызова **setlocale** между перезапускаемыми вызовами функций.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
