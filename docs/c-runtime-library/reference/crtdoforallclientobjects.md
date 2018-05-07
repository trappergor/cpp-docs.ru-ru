---
title: _CrtDoForAllClientObjects | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 889c3c4060098927df08d785e85b64e7e7becc2c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Вызывает функцию, предоставляемую приложением, для всех **_CLIENT_BLOCK** типы в куче (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Параметры

*pfn* указатель на предоставленную приложением функцию обратного вызова. Первый параметр для этой функции указывает на данные. Второй параметр является указателем контекста, передаваемое вызову для **_CrtDoForAllClientObjects**.

*контекст* указатель на контекст, предоставляемый приложением для передачи в функцию, предоставляемую приложением.

## <a name="remarks"></a>Примечания

**_CrtDoForAllClientObjects** будет выполняться поиск кучи в связанном списке блоков памяти с **_CLIENT_BLOCK** типа и вызовы найти предоставленную приложением функцию при блок этого типа. Найденный блок и *контекста* передаются как аргументы в функцию, предоставляемую приложением. Во время отладки приложение может отследить определенную группу выделений, явно вызывая отладочные функции кучи для выделения памяти и указывая, что блокам должен назначаться **_CLIENT_BLOCK** блокировку типа. Эти блоки затем могут отслеживаться по отдельности и включаться в разные отчеты об обнаружении утечки и состоянии памяти.

Если **_CRTDBG_ALLOC_MEM_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг не включен, **_CrtDoForAllClientObjects** немедленно возвращает. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtDoForAllClientObjects** удаляются на этапе предварительной обработки.

Дополнительные сведения о **_CLIENT_BLOCK** типа и его можно использовать другие функции отладки, в разделе [типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Если *pfn* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) равно **EINVAL** и функция возвращает значение.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Библиотеки:** отладочные версии только универсальных библиотек времени выполнения C.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
