---
title: _CrtMemDifference
ms.date: 11/04/2016
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: f2c6306bf604737d0ace142674b21845a08e2dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339472"
---
# <a name="crtmemdifference"></a>_CrtMemDifference

Сравнивает два состояния памяти и возвращает их различия (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Параметры

*stateDiff*<br/>
Указатель на **_CrtMemState** структура, используемая для хранения различий между двумя состояниями памяти (возвращается).

*Сервера*<br/>
Указатель на более раннее состояние памяти (**_CrtMemState** структуры).

*новое состояние*<br/>
Указатель на более позднее состояние памяти (**_CrtMemState** структуры).

## <a name="return-value"></a>Возвращаемое значение

Если состояния памяти значительно отличаются, **_CrtMemDifference** возвращает значение TRUE. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

**_CrtMemDifference** функция сравнивает *сервера* и *newState* и сохраняет их различия в *stateDiff*, который можно затем использоваться приложением для обнаружения утечек памяти и других проблем с памятью. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtMemDifference** удаляются во время предварительной обработки.

*новое состояние* и *сервера* должны быть допустимыми указателями на **_CrtMemState** структуры, определенные в файле Crtdbg.h, которая должна быть заполнена, [_CrtMemCheckpoint](crtmemcheckpoint.md)перед вызовом **_CrtMemDifference**. *stateDiff* должен быть указателем на ранее выделенный экземпляр **_CrtMemState** структуры. Если *stateDiff*, *newState*, или *сервера* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается **EINVAL** и функция возвращает значение FALSE.

**_CrtMemDifference** сравнивает **_CrtMemState** поле значения блоков в *сервера* в wadcfg-файле *новое состояние* и сохраняет результат в *stateDiff*. Если количество выделенных типов блоков или общее количество выделенных блоков каждого типа различается в двух состояниях памяти, считается, что состояния значительно отличаются. Разница между максимальными объемами, выделенными когда-либо за один раз для двух состояний и разница между общим числом выделенных блоков для двух состояний также сохраняются в *stateDiff*.

По умолчанию внутренние блоки времени выполнения C (**_CRT_BLOCK**) не включаются в операций состояния памяти. [_CrtSetDbgFlag](crtsetdbgflag.md) функция может использоваться для включения **_CRTDBG_CHECK_CRT_DF** бита **_crtDbgFlag** для учета этих блоков в обнаружения утечек памяти и другие состояния памяти операции. Освободившихся блоков памяти (**_FREE_BLOCK**) не приводят к **_CrtMemDifference** для возврата значения TRUE.

Дополнительные сведения о функциях управления состоянием кучи и **_CrtMemState** структуры, см. в разделе [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** Отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) только.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
