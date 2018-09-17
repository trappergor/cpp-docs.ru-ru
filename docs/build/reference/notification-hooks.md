---
title: Обработчики уведомления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97e471e2de1ecb6ec6664658a2f1c5df09bc8079
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700626"
---
# <a name="notification-hooks"></a>Обработчики уведомления

Обработчики уведомления вызываются перед выполнением следующих действий в вспомогательной подпрограммы:

- Дескриптор, хранимых в библиотеку проверяется см. в разделе, если он уже загружен.

- **LoadLibrary** вызывается, чтобы попытаться загрузить библиотеку DLL.

- **GetProcAddress** вызывается для получения адреса процедуры.

- Возвращает преобразователь задержки импорта загрузки.

Включите обработчика уведомлений:

- При предоставлении нового определения указателя **__pfnDliNotifyHook2** , инициализированный для указания собственной функции, принимающей уведомления.

   \-или -

- Установив указатель **__pfnDliNotifyHook2** вашей функции-обработчика, прежде чем каких-либо вызовов DLL, которая программа отложить загрузку.

Если это уведомление **dliStartProcessing**, функция-обработчик может вернуть:

- NULL

   Вспомогательное приложение по умолчанию обрабатывает загрузку DLL. Это позволяет вызывать только для ознакомительных целей.

- указатель на функцию

   Обойти обработку отложенной загрузки по умолчанию. Это позволяет задавать обработчик загрузки.

Если это уведомление **dliNotePreLoadLibrary**, функция-обработчик может вернуть:

- 0, если требуется только уведомления.

- HMODULE для загружаемой библиотеке DLL, если он загружен самой библиотеки DLL.

Если это уведомление **dliNotePreGetProcAddress**, функция-обработчик может вернуть:

- 0, если требуется только уведомления.

- Адрес импортированной функции, если функция-обработчик получает адреса URL.

Если это уведомление **dliNoteEndProcessing**, функция-ловушка Возвращаемое значение игнорируется.

Если этот указатель инициализирован (ненулевое), вспомогательные нагрузки задержка будет вызывать функцию в определенных точках уведомления во время своего выполнения. Указатель на функцию имеет следующее определение:

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Уведомления передаются в **DelayLoadInfo** Структура функции-обработчика и значение уведомления. Эти данные идентичен тому, который используется вспомогательная подпрограмма задержки загрузки. Значение уведомлений будет иметь одно из значений, определенных в [определение структуры и константы](../../build/reference/structure-and-constant-definitions.md).

## <a name="see-also"></a>См. также

[Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)