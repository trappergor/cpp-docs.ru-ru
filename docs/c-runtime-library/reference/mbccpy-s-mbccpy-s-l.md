---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: 08df395c6978c84b3f53ed0b07ce988afd0249f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341237"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

Копирует один многобайтовый символ из одной строки в другую. Это версии функций [_mbccpy, _mbccpy_l](mbccpy-mbccpy-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Место назначения копирования.

*buffSizeInBytes*<br/>
Размер буфера назначения.

*pCopied*<br/>
Заполняется числом скопированных байтов (1 или 2 в случае успешного выполнения). Пройдите **NULL,** если вас не волнует номер.

*src*<br/>
Многобайтовый символ для копирования.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи. Если *src* или *dest* **null,** или если больше, чем **buffSizeinBytes** байты будут скопированы на *dest*, то недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции возвращают **EINVAL** и **errno** устанавливается **eINVAL**.

## <a name="remarks"></a>Remarks

Функция **_mbccpy_s** копирует один мультибайтный символ от *src* до *dest.* Если *src* не указывает на свинец байт мультибайтного персонажа, определяемого неявным призывом [к _ismbblead,](ismbblead-ismbblead-l.md)то один байт, на который указывает *src,* скопирован. Если *src* указывает на свинцовые байт, но следующий байт 0 и, таким образом, недействительным, то 0 скопирован до *dest*, **errno** установлен на **EILSE**, и функция возвращает **EILSE**.

**_mbccpy_s** не придает нулевую терминатор; однако, если *src* указывает на нулевой символ, то этот нулевый копируется до *dest* (это просто обычная копия на одну байт).

Значение в *pCopied* заполнено количеством скопированных байтов. В случае успешного выполнения операции возможны значения 1 и 2. Если **NULL** передается, этот параметр игнорируется.

|*src*|скопированы до *dest*|*pCopied*|Возвращаемое значение|
|-----------|----------------------|---------------|------------------|
|не старший байт|не старший байт|1|0|
|0|0|1|0|
|старший байт, за которым следует не 0|старший байт, за которым следует не 0|2|0|
|старший байт, за которым следует 0|0|1|**EILSEQ**|

Обратите внимание, что вторая строка представляет собой особый случай первой. Также обратите внимание, что таблица предполагает *buffSizeInBytes* >= *pCopied*.

**_mbccpy_s** использует текущий локал для любого поведения, зависящем от локализуемого. **_mbccpy_s_l** идентичен **_mbccpy_s** за исключением того, что **_mbccpy_s_l** использует локал, передаваемый для любого поведения, зависящем от локального.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Сопоставляется макросу или встраиваемой функции.|**_mbccpy_s**|Сопоставляется макросу или встраиваемой функции.|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
