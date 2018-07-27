---
title: _CrtMemDifference | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66bb770c2f24c0312277d23c14beef09e2265f88
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32398058"
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

*oldState*<br/>
Указатель на более раннее состояние памяти (**_CrtMemState** структуры).

*новое состояние*<br/>
Указатель на более позднее состояние памяти (**_CrtMemState** структуры).

## <a name="return-value"></a>Возвращаемое значение

Если состояния памяти значительно отличаются, **_CrtMemDifference** возвращает значение TRUE. В противном случае функция возвращает значение FALSE.

## <a name="remarks"></a>Примечания

**_CrtMemDifference** функция сравнивает *oldState* и *новое состояние* и сохраняет их различия в *stateDiff*, который можно затем будет использоваться приложением для обнаружения утечек памяти и других проблем с памятью. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtMemDifference** удаляются на этапе предварительной обработки.

*новое состояние* и *oldState* должны быть допустимыми указателями на **_CrtMemState** структуры, определенные в файле Crtdbg.h, которая должна быть заполнена, [_CrtMemCheckpoint](crtmemcheckpoint.md)перед вызовом **_CrtMemDifference**. *stateDiff* должен быть указателем на ранее выделенный экземпляр **_CrtMemState** структуры. Если *stateDiff*, *новое состояние*, или *oldState* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) равно **EINVAL** и функция возвращает значение FALSE.

**_CrtMemDifference** сравнивает **_CrtMemState** поле значения блоков в *oldState* с позициями в *новое состояние* и сохраняет результат в *stateDiff*. Если количество выделенных типов блоков или общее количество выделенных блоков каждого типа различается в двух состояниях памяти, считается, что состояния значительно отличаются. Разница между максимальными объемами, выделенными когда-либо за один раз для двух состояний и разница между общим числом выделенных блоков для двух состояний, также сохраняются в *stateDiff*.

По умолчанию внутренние блоки времени выполнения C (**_CRT_BLOCK**) не включаются в операций состояния памяти. [_CrtSetDbgFlag](crtsetdbgflag.md) функцию можно использовать для включения **_CRTDBG_CHECK_CRT_DF** бита **_crtDbgFlag** для учета этих блоков в процессе обнаружения утечки и других состояния памяти операции. Освободившихся блоков памяти (**_FREE_BLOCK**) не приводят к **_CrtMemDifference** для возврата значения TRUE.

Дополнительные сведения о функциях состояния кучи и **_CrtMemState** структуры см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
