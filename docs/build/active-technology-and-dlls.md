---
title: "Технология Active и библиотеки DLL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44dcc58aed4025af2e3e2177e978633c13f0ef20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="active-technology-and-dlls"></a>Технология Active и библиотеки DLL
Технология Active размещение сервера объектов внутри библиотеки DLL. Этот тип сервера, называется сервером в процессе. MFC не полностью поддерживает внутрипроцессные серверы для всех функций визуального редактирования, главным образом, поскольку Active-технология предоставляет возможности для сервера в контейнер основной цикл обработки сообщений. MFC требуется доступ к цикл обработки сообщений приложения-контейнера для поддержки сочетаний клавиш и обработку времени простоя.  
  
 При создании сервера автоматизации и сервер не имеет пользовательского интерфейса, можно использовать ваш сервер в процессе и помещать его полностью в библиотеку DLL.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Серверы автоматизации](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>См. также  
 [DLL в Visual C++](../build/dlls-in-visual-cpp.md)