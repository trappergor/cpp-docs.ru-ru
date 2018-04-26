---
title: _CrtMemDumpAllObjectsSince | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30d502daad881417035a10b0a7ef3f4efcc41b4f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

*состояние* указатель на состояние кучи, чтобы начать формирование дампа из или **NULL**.

## <a name="remarks"></a>Примечания

**_CrtMemDumpAllObjectsSince** функция выводит сведения о заголовке отладки объектов, помещенных в кучу в понятной пользователю форме. Данные дампа могут использоваться приложением для отслеживания операций выделения памяти и выявления проблем с памятью. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtMemDumpAllObjectsSince** удаляются на этапе предварительной обработки.

**_CrtMemDumpAllObjectsSince** использует значение *состояние* параметр, чтобы определить, где для инициации операции дампа. Чтобы начать формирование дампа из указанного состояния кучи, *состояние* параметр должен быть указателем на **_CrtMemState** структуру, которая должна быть заполнена, [_CrtMemCheckpoint](crtmemcheckpoint.md) перед **_CrtMemDumpAllObjectsSince** был вызван. Когда *состояние* — **NULL**, функция начинает дампа с начала выполнения программы.

Если приложение установило функция-ловушка дампа путем вызова [_CrtSetDumpClient](crtsetdumpclient.md), то каждый раз **_CrtMemDumpAllObjectsSince** выводит сведения о **_CLIENT_BLOCK** тип блока, он вызывает функцию дампа, предоставляемую приложением. По умолчанию внутренние блоки времени выполнения C (**_CRT_BLOCK**) не включаются в операции дампа памяти. [_CrtSetDbgFlag](crtsetdbgflag.md) функцию можно использовать для включения **_CRTDBG_CHECK_CRT_DF** бита **_crtDbgFlag** для учета этих блоков. Кроме того, блоки, помеченные как освобожденные или игнорируемые (**_FREE_BLOCK**, **_IGNORE_BLOCK**), в дамп памяти не включаются.

Дополнительные сведения о функциях состояния кучи и **_CrtMemState** структуры см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

Пример использования **_CrtMemDumpAllObjectsSince**, в разделе [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
