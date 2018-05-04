---
title: _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64 | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfindnext
- _findnext
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- findnext
- _wfindnext32i64
- _tfindnext64i32
- findnext32
- findnext32i64
- wfindnext64i32
- _wfindnext
- tfindnext64
- findnexti64
- _findnexti64
- _tfindnexti64
- _findnext64i32
- tfindnexti64
- tfindnext32
- _wfindnext64i32
- findnext64i32
- _findnext
- _tfindnext32i64
- _wfindnext64
- wfindnext
- wfindnext32
- tfindnext32i64
- _findnext64
- _tfindnext64
- _wfindnext32
- findnext64
- _findnext32i64
- tfindnext
- wfindnexti64
- tfindnext64i32
- _tfindnext32
- wfindnext32i64
- wfindnext64
- _wfindnexti64
- _tfindnext
- _findnext32
dev_langs:
- C++
helpviewer_keywords:
- _wfindnexti64 function
- _tfindnext32 function
- wfindnexti64 function
- _wfindnext32i64 function
- findnext32i64 function
- tfindnext64i32 function
- _tfindnext64i32 function
- _findnext function
- findnext64i32 function
- _tfindnext function
- findnext32 function
- tfindnext32 function
- _findnext32 function
- _tfindnext32i64 function
- _wfindnext function
- tfindnext function
- _findnext64 function
- findnext64 function
- _findnext64i32 function
- wfindnext32i64 function
- findnext function
- wfindnext32 function
- _wfindnext64i32 function
- findnexti64 function
- _wfindnext64 function
- _findnext32i64 function
- _findnexti64 function
- _tfindnext64 function
- wfindnext64i32 function
- tfindnexti64 function
- wfindnext64 function
- wfindnext function
- tfindnext64 function
- _wfindnext32 function
- tfindnext32i64 function
- _tfindnexti64 function
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 540ec2aae5e13df68438c74e0371e91326e9bb0a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="findnext-findnext32-findnext32i64-findnext64-findnext64i32-findnexti64-wfindnext-wfindnext32-wfindnext32i64-wfindnext64-wfindnext64i32-wfindnexti64"></a>_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64

Найти следующее имя, если таковое имеется, которое соответствует *filespec* аргумент в предыдущем вызове [_findfirst](findfirst-functions.md), а затем изменить *fileinfo* содержимое структуры соответствующим образом.

## <a name="syntax"></a>Синтаксис

```C
int _findnext(
   intptr_t handle,
   struct _finddata_t *fileinfo
);
int _findnext32(
   intptr_t handle,
   struct _finddata32_t *fileinfo
);
int _findnext64(
   intptr_t handle,
   struct __finddata64_t *fileinfo
);
int _findnexti64(
   intptr_t handle,
   struct __finddatai64_t *fileinfo
);
int _findnext32i64(
   intptr_t handle,
   struct _finddata32i64_t *fileinfo
);
int _findnext64i32(
   intptr_t handle,
   struct _finddata64i32_t *fileinfo
);
int _wfindnext(
   intptr_t handle,
   struct _wfinddata_t *fileinfo
);
int _wfindnext32(
   intptr_t handle,
   struct _wfinddata32_t *fileinfo
);
int _wfindnext64(
   intptr_t handle,
   struct _wfinddata64_t *fileinfo
);
int _wfindnexti64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext32i64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext64i32(
   intptr_t handle,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Параметры

*Дескриптор*<br/>
Дескриптор поиска, возвращенный предыдущим вызовом **_findfirst**.

*FileInfo*<br/>
Буфер сведений о файле.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха возвращает 0. В противном случае возвращается значение -1 и задает **errno** значение, указывающее причину сбоя. Возможные коды ошибок приведены в следующей таблице.

|Значение errno|Условие|
|-|-|
**EINVAL**|Недопустимый параметр: *fileinfo* было **NULL**. Или операционная система возвратила непредвиденную ошибку.
**ENOENT**|Больше не удалось найти ни одного соответствующего файла.
**ENOMEM**|Недостаточно памяти или превышена длина имени файла **MAX_PATH**.

Если передан недопустимый параметр, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Примечания

Необходимо вызвать [_findclose](findclose.md) после завершения работы с помощью **_findfirst** или **_findnext** функцию (или все варианты). Она освобождает ресурсы, используемые этими функциями в приложении.

Варианты этих функций с **w** префикс версии для расширенных символов; в противном случае они совпадают с соответствующими Однобайтовая функциям.

Варианты этих функций поддерживают 32- или 64-разрядные типы времени и 32- или 64-разрядные размеры файлов. Первый числовой суффикс (**32** или **64**) указывает размер времени используется тип; второй суффикс **i32** или **i64**, указывающее, представлен ли размер файла как 32-разрядная или 64-разрядное целое число. Сведения о том, какие версии поддерживают 32- и 64-разрядные типы времени и размеры файлов, см. в следующей таблице. Варианты, использующие 64-разрядный тип времени, допускают значение даты создания файла до 23:59:59 31 декабря 3000 года, время в формате UTC; варианты, использующие 32-разрядные типы, могут представлять дату только до 23:59:59 18 января 2038 года, время в формате UTC. Полночь 1 января 1970 года — нижняя граница диапазона дат для всех этих функций.

Если у вас нет особых причин для использования версии, указывающие размер времени явно, используйте **_findnext** или **_wfindnext** или, если необходима поддержка размеров файлов больше 3 ГБ, используйте **_ findnexti64** или **_wfindnexti64**. Все эти функции используют 64-разрядный тип времени. В предыдущих версиях эти функции использовали 32-разрядный тип времени. Если это критическое изменение для приложения, можно определить **_USE_32BIT_TIME_T** для получения старого поведения. Если **_USE_32BIT_TIME_T** определен, **_findnext**, **_finnexti64** и соответствующие версии Юникода используют 32-разрядное время.

### <a name="time-type-and-file-length-type-variations-of-findnext"></a>Варианты типов времени и типов длины файлов в функции _findnext

|Функции|**_USE_32BIT_TIME_T** определенные?|Тип времени|Тип длины файла|
|---------------|----------------------------------|---------------|----------------------|
|**_findnext**, **_wfindnext**|Не определено|64-разрядная|32-разрядная|
|**_findnext**, **_wfindnext**|Определено|32-разрядная|32-разрядная|
|**_findnext32**, **_wfindnext32**|Не затрагивается определением макроса|32-разрядная|32-разрядная|
|**_findnext64**, **_wfindnext64**|Не затрагивается определением макроса|64-разрядная|64-разрядная|
|**_findnexti64**, **_wfindnexti64**|Не определено|64-разрядная|64-разрядная|
|**_findnexti64**, **_wfindnexti64**|Определено|32-разрядная|64-разрядная|
|**_findnext32i64**, **_wfindnext32i64**|Не затрагивается определением макроса|32-разрядная|64-разрядная|
|**_findnext64i32**, **_wfindnext64i32**|Не затрагивается определением макроса|64-разрядная|32-разрядная|

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindnext**|**_findnext**|**_findnext**|**_wfindnext**|
|**_tfindnext32**|**_findnext32**|**_findnext32**|**_wfindnext32**|
|**_tfindnext64**|**_findnext64**|**_findnext64**|**_wfindnext64**|
|**_tfindnexti64**|**_findnexti64**|**_findnexti64**|**_wfindnexti64**|
|**_tfindnext32i64**|**_findnext32i64**|**_findnext32i64**|**_wfindnext32i64**|
|**_tfindnext64i32**|**_findnext64i32**|**_findnext64i32**|**_wfindnext64i32**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_findnext**|\<io.h>|
|**_findnext32**|\<io.h>|
|**_findnext64**|\<io.h>|
|**_findnexti64**|\<io.h>|
|**_findnext32i64**|\<io.h>|
|**_findnext64i32**|\<io.h>|
|**_wfindnext**|\<io.h> или \<wchar.h>|
|**_wfindnext32**|\<io.h> или \<wchar.h>|
|**_wfindnext64**|\<io.h> или \<wchar.h>|
|**_wfindnexti64**|\<io.h> или \<wchar.h>|
|**_wfindnext32i64**|\<io.h> или \<wchar.h>|
|**_wfindnext64i32**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Системные вызовы](../../c-runtime-library/system-calls.md)<br/>
[Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)<br/>
