---
title: _findclose
ms.date: 11/04/2016
apiname:
- _findclose
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
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: 29010f8a502d463eeb6ca98837a1b7dae9f5ae6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538116"
---
# <a name="findclose"></a>_findclose

Закрывает указанный дескриптор поиска и освобождает связанные ресурсы.

## <a name="syntax"></a>Синтаксис

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Параметры

*Дескриптор*<br/>
Дескриптор поиска, возвращенный предыдущим вызовом **_findfirst**.

## <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения **_findclose** возвращает 0. В противном случае возвращается значение -1 и задает **errno** для **ENOENT**, может быть найден, указывающее, что больше нет соответствующего файла.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Системные вызовы](../../c-runtime-library/system-calls.md)<br/>
[Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)<br/>
