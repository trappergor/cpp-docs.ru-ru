---
title: _setmaxstdio | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c0f54f43b0abb5fff2d13233847b45acdb5f0be
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="setmaxstdio"></a>_setmaxstdio

Задает максимальное количество одновременно открытых файлов на **stdio** уровне.

## <a name="syntax"></a>Синтаксис

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>Параметры

*newmax*<br/>
Новое максимальное количество одновременно открытых файлов на **stdio** уровне.

## <a name="return-value"></a>Возвращаемое значение

Возвращает *newmax* в случае успешного выполнения; в противном случае значение -1.

Если *newmax* — меньше, чем **_IOB_ENTRIES** или выше, а затем вызывается максимальное число дескрипторов, доступные в операционной системе, обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает -1 и задает **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Setmaxstdio** функция изменяет максимальное значение количества файлов, которые могут быть одновременно открыты на **stdio** уровне.

Ввод-вывод среды выполнения C теперь поддерживает большее число открытых файлов на базе платформ Win32, чем в предыдущих версиях. До 2048 файлы могут быть открыты одновременно в [уровень lowio](../../c-runtime-library/low-level-i-o.md) (то есть, открытия и доступ с помощью параметра **_open**, **_вопросы**, **_write**, семейство функций ввода-вывода и так далее). До 512 файлы могут быть открыты одновременно в [уровень stdio](../../c-runtime-library/stream-i-o.md) (то есть, открытия и доступ с помощью параметра **fopen**, **fgetc**, **fputc** функции из семейства и так далее). Ограничение в 512 открытых файлов на **stdio** можно увеличить уровень с более 2048 с помощью параметра **_setmaxstdio** функции.

Поскольку **stdio**-на уровне функций, таких как **fopen**, построены на основе **lowio** функции, максимум, равный 2048 является жесткий верхний предел для числа одновременно открывайте файлы, полученные через библиотеки C времени выполнения.

> [!NOTE]
> Это пороговое значение может превышать ограничения, поддерживаемые определенной конфигурацией и платформой Win32.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В разделе [_getmaxstdio](getmaxstdio.md) пример использования **_setmaxstdio**.

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
