---
title: fsetpos
ms.date: 4/2/2020
api_name:
- fsetpos
- _o_fsetpos
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
- fsetpos
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
ms.openlocfilehash: 22b8cebd0154c0dbfc3d21843380ebc9a139059a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345722"
---
# <a name="fsetpos"></a>fsetpos

Задает индикатор позиции в потоке.

## <a name="syntax"></a>Синтаксис

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*pos*<br/>
Хранилище индикатора позиции.

## <a name="return-value"></a>Возвращаемое значение

В случае **успеха, fsetpos** возвращает 0. При сбое функция возвращает ненулевое значение и устанавливает **errno** к одной из следующих констант манифеста (определяется в ERRNO. H): **EBADF**, что означает, что файл недоступен или объект, на который указывает *поток,* не является достоверной структурой файла; или **EINVAL**, что означает недействительное значение для *потока* или *pos* было пройдено. Если передан недопустимый параметр, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **fsetpos** устанавливает индикатор позиции файла для *потока* к значению *pos,* который получен в предыдущем вызове к **fgetpos** против *потока.* Функция очищает конечный индикатор и отменяет любые эффекты [ungetc](ungetc-ungetwc.md) на *потоке.* После вызова **fsetpos**следующей операцией в *потоке* может быть ввод или выход.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fgetpos](fgetpos.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
