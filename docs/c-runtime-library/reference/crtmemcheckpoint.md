---
title: _CrtMemCheckpoint | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 80f9d0b88e5bf1195ca8097e4cfbab5ba97942d7
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

Получает текущее состояние отладочной кучи и сохраняет его в предоставленной приложением **_CrtMemState** структуры (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Параметры

*состояние* указатель **_CrtMemState** структуры для заполнения контрольными точками памяти.

## <a name="remarks"></a>Примечания

**_CrtMemCheckpoint** функция создает моментальный снимок текущего состояния отладочной кучи в любой момент. Этот моментальный снимок могут использовать другие функции управления состоянием кучи, такие как [_CrtMemDifference](crtmemdifference.md), для обнаружения утечек памяти и других проблем. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtMemState** удаляются на этапе предварительной обработки.

Приложение должно передать указатель в выделенный ранее экземпляр **_CrtMemState** структуры, определенные в файле Crtdbg.h в *состояние* параметра. Если **_CrtMemCheckpoint** возникает ошибка при создании контрольной точки, функция создает **_CRT_WARN** отладки отчет с описанием проблемы.

Дополнительные сведения о функциях состояния кучи и **_CrtMemState** структуры см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Если *состояние* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) равно **EINVAL** и функция возвращает значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** только отладочные версии UCRT.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
