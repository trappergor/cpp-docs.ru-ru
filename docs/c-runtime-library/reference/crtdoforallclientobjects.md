---
title: _CrtDoForAllClientObjects
ms.date: 11/04/2016
api_name:
- _CrtDoForAllClientObjects
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
ms.openlocfilehash: 4626df0db1956efd26ee267cb8cacf8ea4a4570c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942533"
---
# <a name="_crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Вызывает функцию, предоставляемую приложением, для всех типов **_CLIENT_BLOCK** в куче (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Параметры

*PFN*<br/>
Указатель на функцию обратного вызова функции, предоставляемой приложением. Первый параметр для этой функции указывает на данные. Второй параметр — это указатель контекста, который передается в вызов **_CrtDoForAllClientObjects**.

*context*<br/>
Указатель на контекст, предоставляемый приложением, для передачи в функцию, предоставляемую приложением.

## <a name="remarks"></a>Примечания

Функция **_CrtDoForAllClientObjects** выполняет поиск блоков памяти в связанном списке кучи с типом **_CLIENT_BLOCK** и вызывает функцию, предоставляемую приложением, при обнаружении блока этого типа. Найденный блок и параметр *контекста* передаются в качестве аргументов функции, предоставляемой приложением. Во время отладки приложение может относить определенную группу выделений путем явного вызова отладочных функций кучи для выделения памяти и указания того, что блокам назначается тип блока **_CLIENT_BLOCK** . Эти блоки затем могут отслеживаться по отдельности и включаться в разные отчеты об обнаружении утечки и состоянии памяти.

Если битовое поле **_CRTDBG_ALLOC_MEM_DF** флага [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) не включено, **_CrtDoForAllClientObjects** немедленно возвращает значение. Если [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtDoForAllClientObjects** удаляются во время предварительной обработки.

Дополнительные сведения о типе **_CLIENT_BLOCK** и способах его использования другими функциями отладки см. в разделе [типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Если *PFN* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметру [_doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается значение **еинвал** , а функция возвращает.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>, \<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

**Libraries** Отладочные версии только универсальных библиотек времени выполнения C.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[Функции создания отчетов о состоянии кучи](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
