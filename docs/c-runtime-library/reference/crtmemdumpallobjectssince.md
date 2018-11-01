---
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: 7de0ee9ff166af6336a8d14aa0dbd07dbd7d23fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526052"
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Записывает в дамп сведения об объектах в куче с начала выполнения программы или перехода в указанное состояние кучи (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Параметры

*state*<br/>
Указатель на состояние кучи, при наступлении которого должен начинаться дамп, или **NULL**.

## <a name="remarks"></a>Примечания

**_CrtMemDumpAllObjectsSince** функция помещает в дамп данные заголовка отладки объектов, помещенных в кучу в понятной пользователю форме. Данные дампа могут использоваться приложением для отслеживания операций выделения памяти и выявления проблем с памятью. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtMemDumpAllObjectsSince** удаляются во время предварительной обработки.

**_CrtMemDumpAllObjectsSince** использует значение *состояние* параметр, чтобы определить, куда начинаться операция дампа. Должен начинаться дамп указанного состояния кучи, *состояние* параметр должен быть указателем на **_CrtMemState** структуру, которая должна быть заполнена, [_CrtMemCheckpoint](crtmemcheckpoint.md) перед **_CrtMemDumpAllObjectsSince** был вызван. Когда *состояние* — **NULL**, функция начинает запись дампа с начала выполнения программы.

Если приложение установило функция-ловушка дампа, вызвав [_CrtSetDumpClient](crtsetdumpclient.md), то каждый раз, **_CrtMemDumpAllObjectsSince** помещает в дамп данные о **_CLIENT_BLOCK** тип блока, он вызывает функцию дампа, предоставляемую приложением. По умолчанию внутренние блоки времени выполнения C (**_CRT_BLOCK**) не включаются в операции с дампом памяти. [_CrtSetDbgFlag](crtsetdbgflag.md) функция может использоваться для включения **_CRTDBG_CHECK_CRT_DF** бита **_crtDbgFlag** для учета этих блоков. Кроме того, блоки, помеченные как освобожденные или игнорируемые (**_FREE_BLOCK**, **_IGNORE_BLOCK**), в дамп памяти не включаются.

Дополнительные сведения о функциях управления состоянием кучи и **_CrtMemState** структуры, см. в разделе [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtMemDumpAllObjectsSince**, см. в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
