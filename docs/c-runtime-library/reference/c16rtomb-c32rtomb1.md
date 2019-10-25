---
title: c16rtomb, c32rtomb
ms.date: 10/22/2019
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
ms.openlocfilehash: 8f480d9b450b528275fea78ae878269fa6a4fa54
ms.sourcegitcommit: 0a5518fdb9d87fcc326a8507ac755936285fcb94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72811064"
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb

Преобразование расширенного символа UTF-16 или UTF-32 в многобайтовый символ UTF-8.

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

*мбчар*\
Указатель на массив для хранения преобразованного многобайтового символа UTF-8.

*wchar*\
Расширенный символ для преобразования.

\ *состояния*
Указатель на объект **mbstate_t** .

## <a name="return-value"></a>Возвращаемое значение

Число байтов, хранящихся в объекте массива *мбчар*, включая любые последовательности сдвигов. Если параметр *WCHAR* не является допустимым расширенным символом, возвращается значение (**size_t**) (-1 **),** параметру « **еилсек**» присваивается значение « *State* ».

## <a name="remarks"></a>Заметки

Функция **c16rtomb** преобразует символ « *WCHAR* » UTF-16 Le в эквивалентную последовательность недопустимых символов UTF-8. Если *мбчар* не является пустым указателем, функция сохраняет преобразованную последовательность в объекте массива, на который указывает *мбчар*. До **MB_CUR_MAX** байт хранятся в *мбчар*, а *State* — в полученном состоянии многобайтовых сдвигов.

Если параметр *WCHAR* является расширенным символом NULL, то при необходимости сохраняется последовательность, необходимая для восстановления первоначального состояния сдвига, а затем символ null. для *состояния* задается начальное состояние преобразования. Функция **c32rtomb** идентична, но ПРЕОБРАЗУЕТ символ UTF-32.

Если *мбчар* является пустым указателем, поведение эквивалентно вызову функции, которая заменяет внутренний буфер для *мбчар* и широкий символ NULL для *WCHAR*.

Объект состояния преобразования *состояния* позволяет выполнять последующие вызовы этой функции и других перезапускаемых функций, которые сохраняют состояние сдвига многобайтовых выходных символов. При использовании перезапускаемых и незапускаемых функций результаты не определены.

Для преобразования символов UTF-16 в многобайтовые символы, отличные от UTF-8, используйте функции [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md), [wcstombs_s или _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) .

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**c16rtomb**, **c32rtomb**|C, C++: \<uchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../compatibility.md).

## <a name="see-also"></a>См. также

\ [преобразования данных](../data-conversion.md)
[Языковой стандарт](../locale.md)\
[Интерпретация последовательностей многобайтовых символов](../interpretation-of-multibyte-character-sequences.md)\
[mbrtoc16, mbrtoc32](mbrtoc16-mbrtoc323.md)\
[wcrtomb](wcrtomb.md)\
[wcrtomb_s](wcrtomb-s.md)
