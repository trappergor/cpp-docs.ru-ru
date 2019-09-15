---
title: _findclose
ms.date: 11/04/2016
api_name:
- _findclose
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _findclose
- findclose
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
ms.openlocfilehash: c67336cc12bcdee754edd40b91078faa83a17984
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957325"
---
# <a name="_findclose"></a>_findclose

Закрывает указанный дескриптор поиска и освобождает связанные ресурсы.

## <a name="syntax"></a>Синтаксис

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>Параметры

*справиться*<br/>
Маркер поиска, возвращенный предыдущим вызовом **_findfirst**.

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **_findclose** возвращает 0. В противном случае возвращается значение-1 **и устанавливается значение** **еноент**, указывающее, что больше не удалось найти соответствующие файлы.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_findclose**|\<io.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Системные вызовы](../../c-runtime-library/system-calls.md)<br/>
[Функции поиска имени файла](../../c-runtime-library/filename-search-functions.md)<br/>
