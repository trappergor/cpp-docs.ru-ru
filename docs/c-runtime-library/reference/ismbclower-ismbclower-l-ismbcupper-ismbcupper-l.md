---
title: _ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l
ms.date: 11/04/2016
apiname:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbcupper
- _ismbclower
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
ms.openlocfilehash: 29a1e97f4583808931e5228a6905aed7c0a62702
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431867"
---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower, _ismbclower_l, _ismbcupper, _ismbcupper_l

Проверяет, имеет ли многобайтовый символ нижний или верхний регистр.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _ismbclower(
   unsigned int c
);
int _ismbclower_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcupper(
   unsigned int c
);
int _ismbcupper_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ, который требуется проверить.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращает ненулевое значение, если символ удовлетворяет условию теста, или 0, если не удовлетворяет. Если *c*< = 255 и есть соответствующая **_ismbb** подпрограммы (например, **_ismbcalnum** соответствует **_ismbbalnum**), результат является возвращаемым значением соответствующего **_ismbb** подпрограммы.

## <a name="remarks"></a>Примечания

Каждая из этих функций проверяет определенный многобайтовый символ на соответствие заданному условию.

Версии этих функций с **_l** суффиксом идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта для поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

|Подпрограмма|Условие теста|Пример кодовой страницы 932|
|-------------|--------------------|---------------------------|
|**_ismbclower**|Строчные буквы|Возвращает ненулевое значение, только если *c* — это — однобайтовое представление буквы нижнего регистра английского алфавита ASCII: 0x61 < =*c*< = 0x7A.|
|**_ismbclower_l**|Строчные буквы|Возвращает ненулевое значение, только если *c* — это — однобайтовое представление буквы нижнего регистра английского алфавита ASCII: 0x61 < =*c*< = 0x7A.|
|**_ismbcupper**|Прописные буквы|Возвращает ненулевое значение, только если *c* — это — однобайтовое представление прописные буквы английского ASCII: 0x41 < =*c*< = 0x5A.|
|**_ismbcupper_l**|Прописные буквы|Возвращает ненулевое значение, только если *c* — это — однобайтовое представление прописные буквы английского ASCII: 0x41 < =*c*< = 0x5A.|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbclower**|\<mbstring.h>|
|**_ismbclower_l**|\<mbstring.h>|
|**_ismbcupper**|\<mbstring.h>|
|**_ismbcupper_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Подпрограммы _ismbc](../../c-runtime-library/ismbc-routines.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
