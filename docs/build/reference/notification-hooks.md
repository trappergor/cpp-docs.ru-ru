---
title: Обработчики уведомления | Документы Microsoft
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
ms.openlocfilehash: 0210c4ee058694594893a029789442c89003da2e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377823"
---
# <a name="notification-hooks"></a>Обработчики уведомления
Обработчики уведомления вызываются перед выполнением следующих действий во вспомогательной подпрограммы:  
  
-   Дескриптор, хранимой в библиотеке проверяется для просмотра, если он уже загружен.  
  
-   **LoadLibrary** вызывается для попытка загрузки библиотеки DLL.  
  
-   **GetProcAddress** вызывается для получения адреса процедуры.  
  
-   Вернитесь в преобразователь задержки импорта загрузки.  
  
 Обработчик уведомления включается:  
  
-   При предоставлении нового определения указателя **__pfnDliNotifyHook2** , инициализированный для указания вашей собственной функции, принимающей уведомления.  
  
     - или -  
  
-   Установив указатель **__pfnDliNotifyHook2** для функция-ловушка до каких-либо вызовов DLL, которая программа отложить загрузку.  
  
 Если уведомление о **dliStartProcessing**, функция обработчика может возвратить:  
  
 NULL  
 Вспомогательный объект по умолчанию обрабатывает загрузку библиотеки DLL. Это полезно для вызова только в ознакомительных целях.  
  
 Указатель на функцию  
 Пропустить обработку отложенной загрузки по умолчанию. Это позволяет предоставить обработчик загрузки.  
  
 Если уведомление о **dliNotePreLoadLibrary**, функция обработчика может возвратить:  
  
-   0, если требуются только информационные уведомления.  
  
-   HMODULE для загружаемой библиотеки DLL, если он загружен самой библиотеки DLL.  
  
 Если уведомление о **dliNotePreGetProcAddress**, функция обработчика может возвратить:  
  
-   0, если требуются только информационные уведомления.  
  
-   Адрес импортированной функции, если функция-обработчик получает адреса URL.  
  
 Если уведомление о **dliNoteEndProcessing**, функция-ловушка Возвращаемое значение игнорируется.  
  
 Если этот указатель инициализирован (не равно нулю), вспомогательные нагрузки задержка будет вызывать функцию в определенных точках уведомления во время своего выполнения. Указатель на функцию имеет следующее определение:  
  
```  
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
  
 Уведомления передаются в **DelayLoadInfo** структуры функции-обработчика и значение уведомления. Эти данные идентичны данным, используемые отложенной загрузки вспомогательной программы. Значение уведомлений будет иметь одно из значений, определенных в [определение структуры и константы](../../build/reference/structure-and-constant-definitions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка ошибок и предупреждений](../../build/reference/error-handling-and-notification.md)