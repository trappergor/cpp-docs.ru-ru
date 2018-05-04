---
title: Технология Active и библиотеки DLL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5e0296b994f7944d5b26e98ba1b0545a03ec55b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="active-technology-and-dlls"></a>Технология Active и библиотеки DLL
Технология Active размещение сервера объектов внутри библиотеки DLL. Этот тип сервера, называется сервером в процессе. MFC не полностью поддерживает внутрипроцессные серверы для всех функций визуального редактирования, главным образом, поскольку Active-технология предоставляет возможности для сервера в контейнер основной цикл обработки сообщений. MFC требуется доступ к цикл обработки сообщений приложения-контейнера для поддержки сочетаний клавиш и обработку времени простоя.  
  
 При создании сервера автоматизации и сервер не имеет пользовательского интерфейса, можно использовать ваш сервер в процессе и помещать его полностью в библиотеку DLL.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Серверы автоматизации](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)