---
title: _strinc, _wcsinc, _mbsinc, _mbsinc_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
dev_langs:
- C++
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 956a0c03d9242d0d8c2912c516e9ba4ed9a06683
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l

Увеличивает строковый указатель на один символ.

> [!IMPORTANT]
> **_mbsinc** и **_mbsinc_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strinc(
   const char *current,
   _locale_t locale
);
wchar_t *_wcsinc(
   const wchar_t *current,
   _locale_t locale
);
unsigned char *_mbsinc(
   const unsigned char *current
);
unsigned char *_mbsinc_l(
   const unsigned char *current,
   _locale_t locale
);

```

### <a name="parameters"></a>Параметры

*Текущий*<br/>
Указатель символа.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает указатель на символ, который следует сразу за *текущей*.

## <a name="remarks"></a>Примечания

**_Mbsinc** функция возвращает указатель на первый байт многобайтового символа, который следует сразу за *текущей*. **_mbsinc** распознает последовательности многобайтовых символов в соответствии с [многобайтовой кодовой страницей](../../c-runtime-library/code-pages.md) , в настоящий момент используется; **_mbsinc_l** идентичен, за исключением того, что она использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Универсальная текстовая функция **_tcsinc**, определенный в файле Tchar.h, сопоставляется **_mbsinc** Если **_MBCS** определен, или к **_wcsinc** Если **_UNICODE** был определен. В противном случае **_tcsinc** сопоставляется **_strinc**. **_strinc** и **_wcsinc** — это одиночные байтов и двухбайтовые версии **_mbsinc**. **_strinc** и **_wcsinc** предоставляются только для этого сопоставления и не должны использоваться иным образом. Дополнительные сведения см. в разделах [Использование универсальных текстовых сопоставлений](../../c-runtime-library/using-generic-text-mappings.md) и [Универсальные текстовые сопоставления](../../c-runtime-library/generic-text-mappings.md).

Если *текущей* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **EINVAL** и задает **errno** для **EINVAL**.

> [!IMPORTANT]
> Эти функции могут быть подвержены угрозам переполнения буфера. Переполнение буфера можно использовать для атак на систему, поскольку оно может привести к несанкционированному повышению уровня привилегий. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsinc**|\<mbstring.h>|
|**_mbsinc_l**|\<mbstring.h>|
|**_strinc**|\<tchar.h>|
|**_wcsinc**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
