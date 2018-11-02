---
title: Автоматизация в библиотеке DLL
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: b9d4f7a71ceb384069fcbef6bf791f0c5fd1b933
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536543"
---
# <a name="automation-in-a-dll"></a>Автоматизация в библиотеке DLL

При выборе параметр автоматизации в мастер библиотек DLL MFC, мастер предоставляет следующее:

- Язык описания объекта starter (. Файл ODL)

- Директива include в файле STDAFX.h Afxole.h

- Реализация `DllGetClassObject` функцию, которая вызывает **AfxDllGetClassObject** функции

- Реализация `DllCanUnloadNow` функцию, которая вызывает **AfxDllCanUnloadNow** функции

- Реализация `DllRegisterServer` функцию, которая вызывает [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) функции

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Серверы автоматизации](../mfc/automation-servers.md)

## <a name="see-also"></a>См. также

[DLL в Visual C++](../build/dlls-in-visual-cpp.md)