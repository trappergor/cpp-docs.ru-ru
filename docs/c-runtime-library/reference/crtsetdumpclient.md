---
title: _CrtSetDumpClient
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 09f319f6298dbec6b229b2923bd86fc9b50314de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342993"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Устанавливает определяемую приложением функцию для помещения в дамп **_CLIENT_BLOCK** введите блоки памяти (только отладочная версия).

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

**_CrtSetDumpClient** функция позволяет приложению прикреплять собственную функцию для дампа объектов, хранящихся в **_CLIENT_BLOCK** блоках памяти времени выполнения C процесса дампа памяти отладки. Таким образом, каждый раз, когда отладки дампа функции, такие как [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) или [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) дампов **_CLIENT_BLOCK** блок памяти, приложения также вызывается функция дампа. **_CrtSetDumpClient** предоставляет приложению простой метод для обнаружения утечек памяти и проверке или reporting содержимое данных, хранящихся в **_CLIENT_BLOCK** блоков. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, вызовы функций **_CrtSetDumpClient** удаляются во время предварительной обработки.

**_CrtSetDumpClient** функция устанавливает новую функцию дампа, определяемые приложением, указанную в *dumpClient* и возвращает функцию дампа, определенную ранее. Пример функции дампа клиентского блока выглядит следующим образом:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*UserPortion* аргумент — указатель на начало данных пользовательской части блока памяти и *blockSize* определяет объем памяти, выделенного блока в байтах. Функция дампа клиентского блока должен возвращать **void**. Указатель на функцию, который передается **_CrtSetDumpClient** имеет тип **_CRT_DUMP_CLIENT**, как определено в Crtdbg.h:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Дополнительные сведения о функциях, работающих с **_CLIENT_BLOCK** блоков памяти типа, см. в разделе [функции-ловушки клиентского блока](/visualstudio/debugger/client-block-hook-functions). Функцию [_CrtReportBlockType](crtreportblocktype.md) можно использовать для получения сведений о типах и подтипов блоков.

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
