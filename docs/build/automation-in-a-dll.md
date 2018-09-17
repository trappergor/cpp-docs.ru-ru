---
title: Автоматизация в библиотеке DLL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cde5d0e400f1bdd3f5a851d47da581380273b04a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717792"
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