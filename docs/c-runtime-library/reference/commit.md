---
title: _commit
ms.date: 11/04/2016
api_name:
- _commit
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
ms.openlocfilehash: b5a417deef48c89751f56feec480e90444728687
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939048"
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

*fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

## <a name="return-value"></a>Возвращаемое значение

**_commit** возвращает 0, если файл был успешно записан на диск. Возвращаемое значение, равное-1, указывает на ошибку.

## <a name="remarks"></a>Примечания

Функция **_commit** заставляет операционную систему записывать файл, связанный с *демоном* , на диск. Этот вызов гарантирует, что указанный файл будет записан незамедлительно, а не по решению операционной системы.

Если *демон демона* является недопустимым дескриптором файла, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает значение-1 **, а** параметру возврата — **значение EBADF**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_commit**|\<io.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_read](read.md)<br/>
[_write](write.md)<br/>
