---
title: _rmdir, _wrmdir
ms.date: 4/2/2020
api_name:
- _wrmdir
- _rmdir
- _o__rmdir
- _o__wrmdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
ms.openlocfilehash: dc9406371da950eb76207d8ddb4a1be8c732098e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338072"
---
# <a name="_rmdir-_wrmdir"></a>_rmdir, _wrmdir

Удаляет каталог.

## <a name="syntax"></a>Синтаксис

```C
int _rmdir(
   const char *dirname
);
int _wrmdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Параметры

*dirname*<br/>
Путь к каталогу, который следует удалить.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает 0, если каталог был успешно удален. Значение возврата -1 указывает на ошибку и **errno** устанавливается на одно из следующих значений:

|Значение errno|Условие|
|-|-|
| **ENOTEMPTY** | Заданный путь не является каталогом, каталог не является пустым или каталог является текущим рабочим каталогом или корневым каталогом. |
| **ENOENT** | Недопустимый путь. |
| **EACCES** | Программа имеет открытый дескриптор каталога. |

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_rmdir** удаляет каталог, указанный *dirname.* Каталог должен быть пустым и не должен являться текущим рабочим или корневым каталогом.

**_wrmdir** является широкохарактерным вариантом **_rmdir;** *аргумент dirname* для **_wrmdir** является широкохарактерной строкой. **_wrmdir** и **_rmdir** ведут себя одинаково иначе.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_trmdir**|**_rmdir**|**_rmdir**|**_wrmdir**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_rmdir**|\<direct.h>|
|**_wrmdir**|\<direct.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

См. пример для функции [_mkdir](mkdir-wmkdir.md).

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
