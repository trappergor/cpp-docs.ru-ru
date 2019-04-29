---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: baf4f8d8234ba744acda20541d37bbc3ed076678
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339459"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Сбрасывает все блоки памяти в отладочной куче в случае утечки памяти (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Возвращаемое значение

**_CrtDumpMemoryLeaks** возвращает TRUE, если найти утечки памяти. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

**_CrtDumpMemoryLeaks** функция определяет, произошла ли утечка памяти с начала выполнения программы. При обнаружении утечки данные заголовка отладки для всех объектов в куче записываются в форме, которую пользователь может прочитать. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtDumpMemoryLeaks** удаляются во время предварительной обработки.

**_CrtDumpMemoryLeaks** часто вызывается в конце выполнения программы, чтобы убедиться, что всю память, выделенная приложением освобожден. Функция может вызываться автоматически при завершении программы, включив **_CRTDBG_LEAK_CHECK_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг с помощью [_CrtSetDbgFlag](crtsetdbgflag.md)функции.

**_CrtDumpMemoryLeaks** вызовы [_CrtMemCheckpoint](crtmemcheckpoint.md) для получения текущего состояния кучи и затем проверяет состояние блоков, которые не были освобождены. При обнаружении Освобожденный блок, **_CrtDumpMemoryLeaks** вызовы [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) для сведений обо всех объектах, выделенных в куче с начала выполнения программы.

По умолчанию внутренние блоки времени выполнения C (**_CRT_BLOCK**) не включаются в операции с дампом памяти. [_CrtSetDbgFlag](crtsetdbgflag.md) функция может использоваться для включения **_CRTDBG_CHECK_CRT_DF** бита **_crtDbgFlag** для учета этих блоков в процесс обнаружения утечек.

Дополнительные сведения о функциях управления состоянием кучи и **_CrtMemState** структуры, см. в разделе [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtDumpMemoryLeaks**, см. в разделе [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
