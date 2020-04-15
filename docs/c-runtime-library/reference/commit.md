---
title: _commit
ms.date: 4/2/2020
api_name:
- _commit
- _o__commit
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _commit
- commit
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
ms.openlocfilehash: f8e13e7fc197c66395556d518ecbd1cd20ac1f77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348620"
---
# <a name="_commit"></a>_commit

Записывает содержимое файла непосредственно на диск.

## <a name="syntax"></a>Синтаксис

```C
int _commit(
   int fd
);
```

### <a name="parameters"></a>Параметры

*Fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

## <a name="return-value"></a>Возвращаемое значение

**_commit** возвращает 0, если файл был успешно промыт на диск. Значение возврата -1 указывает на ошибку.

## <a name="remarks"></a>Remarks

Функция **_commit** заставляет операционную систему записывать файл, связанный с *fd,* на диск. Этот вызов гарантирует, что указанный файл будет записан незамедлительно, а не по решению операционной системы.

Если *fd* является недействительным дескриптором файлов, вызовуется обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращается -1 и **errno** устанавливается на **EBADF**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
