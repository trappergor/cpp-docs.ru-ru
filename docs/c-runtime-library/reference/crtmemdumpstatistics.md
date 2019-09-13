---
title: _CrtMemDumpStatistics
ms.date: 11/04/2016
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
ms.openlocfilehash: 66eb58b65f3fa20e01ad16d68f3fe1baafd8cd04
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739813"
---
# <a name="_crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Помещает в дамп данные заголовка отладки для указанного состояния кучи в понятной пользователю форме (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Параметры

*state*<br/>
Указатель на состояние кучи для создания дампа.

## <a name="remarks"></a>Примечания

Функция **_CrtMemDumpStatistics** выводит данные заголовка отладки для указанного состояния кучи в форме, доступной для чтения пользователем. Статистика дампа может использоваться приложением для отслеживания операций выделения памяти и выявления проблем с памятью. Состояние памяти может содержать состояние определенной кучи или разницу между двумя состояниями. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtMemDumpStatistics** удаляются во время предварительной обработки.

Параметр *State* должен быть указателем на структуру **_CrtMemState** , которая была заполнена с помощью [_CrtMemCheckpoint](crtmemcheckpoint.md) или возвращена [_CrtMemDifference](crtmemdifference.md) перед вызовом **_CrtMemDumpStatistics** . Если параметр *State* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** задается значение, а никакие действия не выполняются. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Дополнительные сведения о функциях состояния кучи и структуре **_CrtMemState** см. в разделе [функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details). Дополнительные сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательные заголовки|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Libraries** Только отладочные версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
