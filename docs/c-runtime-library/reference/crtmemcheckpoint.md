---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: ee435ba3e9e40795280dee0f97feaad32c8b0fc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589521"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

Получает текущее состояние отладочной кучи и сохраняет в предоставленной приложением **_CrtMemState** структуры (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Параметры

*state*<br/>
Указатель на **_CrtMemState** структуры для заполнения контрольными точками памяти.

## <a name="remarks"></a>Примечания

**_CrtMemCheckpoint** функция создает моментальный снимок текущего состояния отладочной кучи в любой момент. Этот моментальный снимок могут использовать другие функции управления состоянием кучи, такие как [_CrtMemDifference](crtmemdifference.md) , для обнаружения утечек памяти и других проблем. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtMemState** удаляются во время предварительной обработки.

Приложение должно передать указатель на ранее выделенный экземпляр **_CrtMemState** структуры, определенные в Crtdbg.h в *состояние* параметра. Если **_CrtMemCheckpoint** возникает ошибка во время создания контрольной точки, функция создает **_CRT_WARN** отладка отчет с описанием проблемы.

Дополнительные сведения о функциях управления состоянием кучи и **_CrtMemState** структуры, см. в разделе [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Если *состояние* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается **EINVAL** и функция возвращает значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** только отладочные версии UCRT.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
