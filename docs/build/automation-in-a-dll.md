---
title: Автоматизация в библиотеке DLL
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
ms.openlocfilehash: dedc832d6726dccf8c0c2e88f9f4d5c67590c1c2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220929"
---
# <a name="automation-in-a-dll"></a>Автоматизация в библиотеке DLL

При выборе параметра "Автоматизация" в мастере библиотек DLL MFC мастер предоставляет следующее:

- Файл языка описания начального объекта (ODL)

- Директива include в файле STDAFX h для Afxole.h

- Реализация функции `DllGetClassObject`, которая вызывает функцию **AfxDllGetClassObject**

- Реализация функции `DllCanUnloadNow`, которая вызывает функцию **AfxDllCanUnloadNow**

- Реализация функции `DllRegisterServer`, которая вызывает функцию [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Серверы автоматизации](../mfc/automation-servers.md)

## <a name="see-also"></a>См. также

[Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)
