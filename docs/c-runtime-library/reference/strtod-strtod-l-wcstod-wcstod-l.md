---
title: strtod, _strtod_l, wcstod, _wcstod_l
ms.date: 4/2/2020
api_name:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
- _o__strtod_l
- _o__wcstod_l
- _o_strtod
- _o_wcstod
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
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
ms.openlocfilehash: a688846d5db4d508327745728f8933c91bfd54e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337668"
---
# <a name="strtod-_strtod_l-wcstod-_wcstod_l"></a>strtod, _strtod_l, wcstod, _wcstod_l

Преобразование строки в значение двойной точности.

## <a name="syntax"></a>Синтаксис

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*strSource*<br/>
Строка, завершающаяся символом NULL, для преобразования.

*endptr*<br/>
Указатель на символ, который останавливает сканирование.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**strtod** возвращает значение номера плавающей точки, за исключением случаев, когда представление может привести к переполнению, и в этом случае функция**возвращается**HUGE_VAL . Знак **HUGE_VAL** соответствует признаку значения, которое не может быть представлено. **strtod** возвращает 0, если не может быть выполнено преобразование или происходит недопосредствение.

**wcstod** возвращает значения аналогично **strtod.** Для обеих функций **errno** устанавливается в **ERANGE,** если происходит переполнение или недопог ели и вызывается недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Подробнее об этом и других кодах возврата читайте [_doserrno, errno, _sys_errlist и _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Remarks

Каждая функция преобразует входного строки *strSource* в **двойной.** Функция **strtod** преобразует *strSource* в двойное значение. **strtod** останавливает чтение строки *strSource* на первом символе, который он не может распознать как часть числа. Это может быть завершающий нуль-символ. **wcstod** является широкохарактерным вариантом **strtod**; его *аргумент strSource* является широкохарактерной строкой. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

Настройка **LC_NUMERIC** категории текущего локализации определяет распознавание символа точки радикса в *strSource.* Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функции без **_l** суффикса используют текущий локали; **_strtod_l** идентичен **_strtod_l** за исключением того, что они используют *местность,* передаваемую вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *endptr* не **является NULL,** указатель на символ, который остановил сканирование хранится в месте, указал на *endptr*. Если преобразование не выполняется (не было найдено действительных цифр или указана недействительная база), значение *strSource* хранится в месте, указанном *endptr.*

**strtod** ожидает *strSource* указать на строку одной из следующих форм:

-*белое пространство* Знак -*знак* *цифры* ,*цифры радикса,* *digits*&#124; цифры *радикса* *digits* --**e** &#124;*sequence* **E** **NAN** -*sign**sign**whitespace* *hexdigits**whitespace**подпишите*- *цифры*, -*белое пространство*,*знак*-**0x** &#124; **0X**,*шестизначные* **INFINITY**- шестизначные - *дигностиксы**радикса* , &#124; *шестизначных дигностиков* *радикса* , п **&#124;** **P****&#124;** *.*

Дополнительное ведущее *белое пространство* может состоять из символов пространства и вкладок, которые игнорируются; *знак* является либо плюсом (к) или минусом (-); *цифры* являются одной или нескольких десятичных цифр; *шестизначные* являются одной или нескольких гексадецичных цифр; *радикс* — это символ точки радикса, либо период (.) в локалью "C" по умолчанию, либо конкретное значение локализующего места, если текущий локаль отличается или когда указан *локализуется локализуется;* *последовательность* представляет собой последовательность алфавитных или подчеркивать символы. В форме десятичной и гексадецкойого числа, если цифры не появляются перед символом точки радикса, по крайней мере один должен появиться после символа точки радикса. В десятичной форме за десятичными цифрами может последовать показатель, состоящий из вступительного письма **(e** или **E)** и опционально подписанного бессчетного числа. В гексадецимальной форме, гексадецимальные цифры могут сопровождаться экспонентом, который состоит из вступительного письма **(р** или **P**) и опционально подписанного гексадецимного целых, который представляет показатель как власть 2. В любой форме, если не появляется ни экспонентная часть, ни символ точки радикса, предполагается, что символ точки радикса следует последней цифре в строке. Дело игнорируется как в формах **INF,** так и **в NAN.** Первый символ, который не подходит одной из этих форм, останавливает сканирование.

Версии UCRT этих функций не поддерживают преобразование букв в стиле Fortran **(d** или **D)** Это нестандартное расширение поддерживалось в более ранних версиях CRT и может оказаться критическим изменением для вашего кода. Версии UCRT поддерживают гексадецичные строки и круглые отключения значений INF и NAN, которые не были поддержаны в предыдущих версиях. Это также может привести к нарушению кода. Например, строка "0x1a" будет интерпретироваться **strtod** как 0.0 в предыдущих версиях, но как 26.0 в версии UCRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strtod,** **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> или &lt;stdlib.h> |
|**wcstod**, **_wcstod_l**|C: &lt;stdlib.h> или &lt;wchar.h> C++: &lt;cstdlib>, &lt;stdlib.h> или &lt;wchar.h> |

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Функции преобразования строк в числовое значение](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
