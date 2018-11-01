---
title: _CrtGetReportHook
ms.date: 11/04/2016
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
ms.openlocfilehash: 0b8b666093807c95312d4328ca9b3043ad1e09df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536764"
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook

Извлекает определяемую клиентом функцию отчетов путем ее прикрепления к процессу создания отчетов среды выполнения языка C (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает текущую определяемую клиентом функцию отчетов.

## <a name="remarks"></a>Примечания

**_CrtGetReportHook** позволяет приложению извлекать текущую функцию отчетов для библиотеки отладки среды выполнения C, процедуры составления отчетности.

Дополнительные сведения о других допускающих подключение функциях среды выполнения и написании собственных определяемых клиентом функциях-ловушках см. в разделе [Написание функций отладочных ловушек](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtSetReportHook**, см. в разделе [отчета](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
