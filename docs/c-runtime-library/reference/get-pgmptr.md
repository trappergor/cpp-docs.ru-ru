---
title: _get_pgmptr | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_pgmptr
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_pgmptr
- _get_pgmptr
dev_langs:
- C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0488e2a7b8cd907872e835abb63e62f29f259455
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397783"
---
# <a name="getpgmptr"></a>_get_pgmptr

Возвращает текущее значение **_pgmptr** глобальной переменной.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_pgmptr( 
   char **pValue 
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на строку для заполнения текущее значение **_pgmptr** переменной.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае ошибки. Если *pValue* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Примечания

Вызывать только **_get_pgmptr** , например если программа содержит точку входа узкий, **main()** или **WinMain()**. **_Pgmptr** глобальная переменная содержит полный путь к исполняемому файлу, связанному с процессом. Дополнительные сведения см. в разделе [_pgmptr _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_pgmptr**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_get_wpgmptr](get-wpgmptr.md)<br/>
