---
title: Автоматизация в библиотеке DLL | Документы Microsoft
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
ms.openlocfilehash: 41c5f31a72cf734296ecb281e0785d415c8043a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360658"
---
# <a name="automation-in-a-dll"></a>Автоматизация в библиотеке DLL
При выборе параметра автоматизации в мастер MFC DLL мастер предоставляет следующее:  
  
-   Язык описания начального объекта (. Файл ODL)  
  
-   Директива include в файле STDAFX.h Afxole.h  
  
-   Реализация `DllGetClassObject` функции, которая вызывает **AfxDllGetClassObject** функции  
  
-   Реализация `DllCanUnloadNow` функции, которая вызывает **AfxDllCanUnloadNow** функции  
  
-   Реализация `DllRegisterServer` функции, которая вызывает [COleObjectFactory::UpdateRegistryAll](../mfc/reference/coleobjectfactory-class.md#updateregistryall) функции  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Серверы автоматизации](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)