---
title: _CrtSetDumpClient | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5fecc90b4b7259f1440a0a0d86277c769c4e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397227"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Устанавливает определяемую приложением функцию для помещения в дамп **_CLIENT_BLOCK** текстовые блоки памяти (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Параметры

*dumpClient*<br/>
Новая, определяемая клиентом функция дампа памяти, которую необходимо прикрепить к отладочному процессу дампа памяти среды выполнения C.

## <a name="return-value"></a>Возвращаемое значение

Возвращает определенную ранее функцию дампа клиентских блоков.

## <a name="remarks"></a>Примечания

**_CrtSetDumpClient** функция позволяет приложению для вывода объектов, хранящихся в его собственную функцию-обработчик **_CLIENT_BLOCK** блоков памяти в C времени выполнения отладки процесса дампа памяти. В результате каждый раз, когда Отладка дампа функции, такие как [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) или [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) дампов **_CLIENT_BLOCK** блок памяти, приложения также вызывается функция дампа. **_CrtSetDumpClient** предоставляет приложению простой метод для обнаружения утечек памяти и проверке или содержимое данные, хранящиеся в reporting **_CLIENT_BLOCK** блоков. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы **_CrtSetDumpClient** удаляются на этапе предварительной обработки.

**_CrtSetDumpClient** функция устанавливает новые определяемые приложением дампа функции, указанной в *dumpClient* и возвращает дампа ранее определенную функцию. Пример функции дампа клиентского блока выглядит следующим образом:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*UserPortion* аргумент — указатель на начало данных пользовательской части блока памяти и *blockSize* указывает размер выделенной памяти блока в байтах. Клиентская функция дампа блок должен возвращать **void**. Указатель на функцию дампа клиента, передаваемое **_CrtSetDumpClient** относится к типу **_CRT_DUMP_CLIENT**, как определено в Crtdbg.h:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Дополнительные сведения о функциях, работающих на **_CLIENT_BLOCK** блоков памяти типа см. в разделе [функции ловушки клиентского блока](/visualstudio/debugger/client-block-hook-functions). Функцию [_CrtReportBlockType](crtreportblocktype.md) можно использовать для получения сведений о типах и подтипов блоков.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
