---
title: c16rtomb c32rtomb1 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs:
- C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3282fb13e5b59ad3214c67410eef5186687114e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

*mbchar*<br/>
Указатель на массив для хранения преобразованного многобайтового символа.

*wchar*<br/>
Расширенный символ для преобразования.

*state*<br/>
Указатель на **mbstate_t** объекта.

## <a name="return-value"></a>Возвращаемое значение

Число байтов, сохраняемых в объекте массива *mbchar*, включая любые последовательности сдвигов. Если *wchar* не является допустимым расширенным символом, значение (**size_t**)(-1) возвращается, **errno** равно **EILSEQ**, а для параметра *состояние* не указан.

## <a name="remarks"></a>Примечания

**C16rtomb** функция преобразует символ UTF-16 *wchar* последовательность эквивалентные обычных символов в текущем языковом стандарте. Если *mbchar* не является пустым указателем, функция сохраняет преобразованную последовательность в объекте массива, на который указывает *mbchar*. До **MB_CUR_MAX** байтов сохраняется в *mbchar*, и *состояние* устанавливается в итоговое состояние многобайтового сдвига.    Если *wchar* является пустым расширенным символом, необходимые для последовательности восстановления начальное состояние сдвига хранится в случае необходимости следуют символ null, и *состояние* присваивается состояние начального преобразования. **C32rtomb** функция идентична, но преобразует символ UTF-32.

Если *mbchar* является пустым указателем, поведение эквивалентно вызову функции, которая заменяет внутренний буфер для *mbchar* и расширенный символ null для *wchar*.

*Состояние* объект состояния преобразования позволяет выполнять последующие вызовы этой функции и других перезапускаемых функций, которые сохраняют состояние сдвига многобайтовых выходных символов. Результаты не определены при совместном использовании перезапускаемых и неперезапускаемых функций или если вызов **setlocale** между вызовами перезапускаемой функции.

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
