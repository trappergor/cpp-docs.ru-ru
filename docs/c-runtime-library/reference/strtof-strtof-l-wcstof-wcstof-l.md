---
title: strtof, _strtof_l, wcstof, _wcstof_l
ms.date: 4/2/2020
api_name:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
- _o__strtof_l
- _o__wcstof_l
- _o_strtof
- _o_wcstof
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
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
ms.openlocfilehash: f61aa0edeadd74a254f906dd745e18b059da7f24
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365138"
---
# <a name="strtof-_strtof_l-wcstof-_wcstof_l"></a>strtof, _strtof_l, wcstof, _wcstof_l

Преобразует строки в значение одиночной точности с плавающей точкой.

## <a name="syntax"></a>Синтаксис

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>Параметры

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtof** возвращает значение номера плавающей точки, за исключением случаев, когда представление может привести к переполнению, и в этом случае функция**возвращается**HUGE_VALF . Знак **HUGE_VALF** соответствует знаку значения, которое не может быть представлено. **strtof** возвращает 0, если не может быть выполнено преобразование или происходит недопосредствение.

**wcstof** возвращает значения аналогично **strtof.** Для обеих функций **errno** устанавливается в **ERANGE,** если происходит переполнение или недопог ели и вызывается недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md)

Дополнительные сведения о кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Каждая функция преобразует строку ввода *strSource* в **поплавок.** Функция **strtof** преобразует *strSource* в одноточное значение. **strtof** перестает читать строку *strSource* на первом символе он не может распознать как часть числа. Это может быть завершающий нуль-символ. **wcstof** является широкохарактерным вариантом **strtof**; его *аргумент strSource* является широкохарактерной строкой. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

Установка **LC_NUMERIC** категории текущего локализации определяет распознавание символа radix в *strSource;* для получения дополнительной информации, [см setlocale, _wsetlocale](setlocale-wsetlocale.md). Функции, которые не имеют **_l** суффикса использовать текущий локали; те, которые имеют суффикс идентичны, за исключением того, что они используют локали, что прошло в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **является NULL,** указатель на символ, который остановил сканирование, хранится в месте, которое указывается *endptr.* Если конверсия не выполняется (не найдено действительных цифр или указана недействительная база), значение *strSource* хранится в месте, указанном *endptr.*

**strtof** *ожидает* strSource указать на строку из следующей формы:

-*белое пространство* Знак -*знак* Цифры и*цифры* [__.__ *цифры* --**e** &#124; **E**-*знак*и *цифры*

*Белое пространство* может состоять из символов пространства и вкладок, которые игнорируются; *знак* либо плюс**+**()**-** или минус (); и *цифры* являются одной или нескольких десятичных цифр. Если перед символом основания системы счисления нет никаких цифр, то после него должна отображаться хотя бы одна цифра. За десятичными цифрами может последовать показатель, состоящий из вступительного письма **(e** или **E)** и опционально подписанного integer. Если не отображается ни экспоненциальная часть, ни символ основания системы счисления, то предполагается, что символ основания системы счисления следует за последней цифрой в строке. Первый символ, который не соответствует этой форме, останавливает сканирование.

Версии UCRT этих функций не поддерживают преобразование букв в стиле Fortran **(d** или **D)** Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<stdlib.h> C++: &lt;cstdlib> или \<stdlib.h>|
|**wcstof**, **_wcstof_l**|C: \<stdlib.h> или \<wchar.h> C++: &lt;cstdlib>, \<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
   Stopped scan at: This stopped it
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
