---
title: _CrtGetDumpClient
ms.date: 11/04/2016
apiname:
- _CrtGetDumpClient
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
apitype: DLLExport
f1_keywords:
- CrtGetDumpClient
- _CrtGetDumpClient
helpviewer_keywords:
- _CrtGetDumpClient function
- CrtGetDumpClient function
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
ms.openlocfilehash: e4700bd936bec97014508c4a971f6e6c278c6a11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550739"
---
# <a name="crtgetdumpclient"></a>_CrtGetDumpClient

Извлекает текущий определяемую приложением функцию для дампа **_CLIENT_BLOCK** введите блоки памяти (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает текущую подпрограмму дампа.

## <a name="remarks"></a>Примечания

**_CrtGetDumpClient** функция извлекает текущую функцию ловушка для дампа объектов, хранящихся в **_CLIENT_BLOCK** блоков памяти для выполнения C процесса дампа памяти отладки.

Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Написание функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtGetDumpClient**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtSetDumpClient](crtsetdumpclient.md)<br/>
