---
title: ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs:
- C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3f9c5e6d9d6f0d910decae904cbbd75d995a6c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404322"
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s, _ctime32_s, _ctime64_s, _wctime_s, _wctime32_s, _wctime64_s

Преобразуют значение времени в строку и настраивают его в соответствии с параметрами локального часового пояса. Это версии функции [ctime, _ctime64, _wctime, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t ctime_s(
   char* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _ctime32_s(
   char* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _ctime64_s(
   char* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime )
;
errno_t _wctime_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _wctime32_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _wctime64_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime
);
```

```cpp
template <size_t size>
errno_t _ctime32_s(
   char (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _ctime64_s(
   char (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime32_s(
   wchar_t (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime64_s(
   wchar_t (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Должен быть достаточно большим для хранения 26 символов. Указатель на результирующую строку символов или **NULL** если:

- *sourceTime* представляет дату перед полуночью 1 января 1970 года в формате UTC.

- Если вы используете **_ctime32_s** или **_wctime32_s** и *sourceTime* представляет дату после 23:59:59 18 января 2038 года, время UTC.

- Если вы используете **_ctime64_s** или **_wctime64_s** и *sourceTime* представляет дату после 23:59:59, 31 декабря 3000 года, время UTC.

- Если вы используете **_ctime_s** или **_wctime_s**, эти функции являются оболочками для предыдущей функции. См. раздел примeчаний.

*numberOfElements*<br/>
Размер буфера.

*sourceTime*<br/>
Указатель на сохраненное время.

## <a name="return-value"></a>Возвращаемое значение

Нуль при успешном завершении. В случае отказа в связи с недопустимым параметром вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, возвращается код ошибки. Коды ошибок определены в файле ERRNO.H; список этих ошибок см. в разделе [errno](../../c-runtime-library/errno-constants.md). Фактические коды ошибок, отображаемые для каждого условия ошибки, представлены в следующей таблице.

## <a name="error-conditions"></a>Условия ошибок

|*buffer*|*numberOfElements*|*sourceTime*|Назад|Значение в *буфера*|
|--------------|------------------------|------------|------------|-----------------------|
|**NULL**|any|any|**EINVAL**|Без изменений|
|Не **NULL** (указывает на допустимый адрес в памяти)|0|any|**EINVAL**|Без изменений|
|Не **значение NULL**|0< size < 26|any|**EINVAL**|Пустая строка|
|Не **значение NULL**|>= 26|NULL|**EINVAL**|Пустая строка|
|Не **значение NULL**|>= 26|< 0|**EINVAL**|Пустая строка|

## <a name="remarks"></a>Примечания

**Ctime_s** функция преобразует значение времени хранится как [time_t](../../c-runtime-library/standard-types.md) структуры в символьную строку. *SourceTime* значение обычно получается из вызова [время](time-time32-time64.md), который возвращает количество секунд, истекших после полуночи (00: 00:00), 1 января 1970 года всеобщего скоординированного времени (UTC). Строка возвращаемого значения содержит ровно 26 символов и имеет следующий вид:

`Wed Jan 02 02:03:55 1980\n\0`

Время в 24-часовом формате. Все поля имеют постоянную ширину. Символ новой строки ("\n") и нуль-символ ("\0") занимают две последние позиции строки.

Преобразованная символьная строка также настраивается согласно параметрам местного часового пояса. В разделе [время](time-time32-time64.md), [_ftime](ftime-ftime32-ftime64.md), и [localtime32_s](localtime-s-localtime32-s-localtime64-s.md) функции для получения сведений о настройке местного времени и [_tzset](tzset.md) функция сведения об определении среды часового пояса и глобальных переменных.

**_wctime32_s** и **_wctime64_s** — это двухбайтовая версия **_ctime32_s** и **_ctime64_s**; возвращают указатель на строку расширенных символов. В противном случае **_ctime64_s**, **_wctime32_s**, и **_wctime64_s** ведут себя идентично **_ctime32_s**.

**ctime_s** — это встраиваемая функция, результатом которого является **_ctime64_s** и **time_t** эквивалентно **__time64_t**. Если вам нужно заставляют компилятор интерпретировать **time_t** как старое 32-разрядное **time_t**, можно определить **_USE_32BIT_TIME_T**. Результате **ctime_s** будет вычисляться как **_ctime32_s**. Это не рекомендуется, поскольку приложение может завершиться с ошибкой после 18-го января 2038 года, и не поддерживается на 64-разрядных платформах.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<time.h>|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<time.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_wctime_s.c
// This program gets the current
// time in time_t form and then uses _wctime_s to
// display the time in string form.

#include <time.h>
#include <stdio.h>

#define SIZE 26

int main( void )
{
   time_t ltime;
   wchar_t buf[SIZE];
   errno_t err;

   time( &ltime );

   err = _wctime_s( buf, SIZE, &ltime );
   if (err != 0)
   {
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);
   }
   wprintf_s( L"The time is %s\n", buf );
}
```

```Output
The time is Fri Apr 25 13:03:39 2003
```

## <a name="see-also"></a>См. также

[Управление временем](../../c-runtime-library/time-management.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
