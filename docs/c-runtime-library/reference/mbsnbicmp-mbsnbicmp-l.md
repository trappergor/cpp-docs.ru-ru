---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
- _o__mbsnbicmp
- _o__mbsnbicmp_l
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
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _mbsnbicmp_l
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
ms.openlocfilehash: 80d2708396cdaeb86c25932c3d13129fb318719a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340577"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

Сравнивает **n** байты двух строк мультибайт-символа и игнорирует случай.

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
|< 0|*string1* подстроки меньше, чем *подстрока2.*|
|0|*string1* подстроки, идентичной *подстроке2.*|
|> 0|*string1* подстроки больше, чем *подстрока string2.*|

При ошибке **_mbsnbicmp** возвращает **_NLSCMPERROR,** которая определяется в String.h и Mbstring.h.

## <a name="remarks"></a>Remarks

Функция **_mbsnbicmp** выполняет обыденное сравнение не более первых *байтов* *строки1* и *строки2.* Сравнение выполняется путем преобразования каждого символа в нижний регистр; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) является дело чувствительных версия **_mbsnbicmp**. Сравнение заканчивается, если окончание нулевого символа достигается в любой строке до сравнения символов *подсчета.* Если строки равны, когда термин null достигается в любой строке до того, как сравниваются символы *подсчета,* более короткая строка меньше.

**_mbsnbicmp** похож на [_mbsnbcmp,](mbsnbcmp-mbsnbcmp-l.md)за исключением того, что он сравнивает строки до *подсчета* байтов, а не символов.

Две строки, содержащие символы, которые расположены между Z и a в таблице ASCII ("[", "\\", "]", "^", "_" и "\`"), сравниваются по-разному в зависимости от их регистра. Например, две строки "ABCDE" и "ABCD" сравнивают один способ, если сравнение является нижним регистром ("abcde" > "abcd") и в другую сторону ("ABCDE" < "ABCD") если он является верхним регистром.

**_mbsnbicmp** распознает последовательности мультибайт-символов в соответствии с [многобайтовым кодом страницы,](../../c-runtime-library/code-pages.md) которая используется в настоящее время. На нее не влияет текущий параметр языкового стандарта.

Если *строка1* или *строка2* является нулевой указателем, **_mbsnbicmp** вызывает недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция **возвращается _NLSCMPERROR** и устанавливает **errno** в **EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
