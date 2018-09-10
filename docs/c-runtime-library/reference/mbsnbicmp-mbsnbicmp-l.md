---
title: _mbsnbicmp, _mbsnbicmp_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs:
- C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43c9da102f81654062518ca8e886aab1c49df623
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314967"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l

Сравнивает **n** байтов многобайтовых символов двух строк и не учитывает регистр.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Параметры

*string1*, *string2*<br/>
Строки с завершающим нулем для сравнения.

*count*<br/>
Число сравниваемых байтов.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение показывает связь между подстроками.

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*string1* подстроки меньше, чем *string2* подстроки.|
|0|*string1* подстроки, идентичен *string2* подстроки.|
|> 0|*string1* больше, чем подстрока *string2* подстроки.|

При возникновении ошибки **_mbsnbicmp** возвращает **_NLSCMPERROR**, которое определено в String.h и Mbstring.h.

## <a name="remarks"></a>Примечания

**_Mbsnbicmp** функция выполняет порядковое сравнение не более первого *число* байт *string1* и *string2*. Сравнение выполняется путем преобразования каждого символа в нижний регистр; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) — с учетом регистра версия **_mbsnbicmp**. Сравнение заканчивается, если достигнут завершающий нуль-символ в любой из строк, прежде чем *число* сравниваются символы. Если строки равны при достижении завершающий нуль-символ в любой из строк, прежде чем *число* символов сравнены, более короткая строка меньше.

**_mbsnbicmp** аналогичен [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md), за исключением того, что она сравнивает строки до *число* байтов, а не по символам.

Две строки, содержащие символы, которые расположены между Z и a в таблице ASCII ("[", "\\", "]", "^", "_" и "\`"), сравниваются по-разному в зависимости от их регистра. Например, две строки «ABCDE» и «ABCD ^» сравниваются с одним результатом, если сравнение производится в нижнем регистре («abcde» > «abcd ^») и с другим («ABCDE» < «ABCD ^») Если производится в верхнем регистре.

**_mbsnbicmp** распознает последовательности многобайтовых символов в соответствии с [многобайтовую кодовую страницу](../../c-runtime-library/code-pages.md) в настоящий момент. На нее не влияет текущий параметр языкового стандарта.

Если параметр *string1* или *string2* является пустым указателем, **_mbsnbicmp** вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает **_NLSCMPERROR** и задает **errno** для **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
