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
ms.openlocfilehash: 378ef3c6218d1f57cd1d817d8895b3ff8b081ecb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105347"
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

Вызывает предоставленную приложением функцию для всех **_CLIENT_BLOCK** типы в куче (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>Параметры

*pfn-имени*<br/>
Указатель на функцию обратного вызова функции, предоставляемой приложением. Первый параметр для этой функции указывает на данные. Второй параметр является указателем контекста, который передается в вызов **_CrtDoForAllClientObjects**.

*context*<br/>
Указатель на контекст, предоставляемый приложением, для передачи в функцию, предоставляемую приложением.

## <a name="remarks"></a>Примечания

**_CrtDoForAllClientObjects** выполняться поиск связанном списке кучи для блоков памяти с **_CLIENT_BLOCK** типа и вызывает предоставленную приложением функцию при блок этого типа находится. Найденный блок и *контекст* параметра передаются как аргументы в функцию, предоставляемую приложением. Во время отладки приложение может отследить определенную группу выделений путем явного вызова отладочные функции кучи для выделения памяти и указания, что блокам должен назначаться **_CLIENT_BLOCK** тип блока. Эти блоки затем могут отслеживаться по отдельности и включаться в разные отчеты об обнаружении утечки и состоянии памяти.

Если **_CRTDBG_ALLOC_MEM_DF** битовое поле [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) флаг не включена, **_CrtDoForAllClientObjects** сразу после его вызова. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtDoForAllClientObjects** удаляются во время предварительной обработки.

Дополнительные сведения о **_CLIENT_BLOCK** типа и его можно использовать другие функции отладки, см. в разделе [типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Если *pfn* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) присваивается **EINVAL** и функция возвращает значение.

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
