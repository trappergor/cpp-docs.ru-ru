---
title: "Построение C/C++ изолированных приложений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76b0c1fa5b509ae495a12fb63164d7da01f402aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications"></a>Построение изолированных приложений C/C++
Изолированное приложение зависит только от side-by-side сборок и привязывается к ним с помощью манифеста. Не является обязательным для приложения следует полностью изолированы для правильной работы в Windows. Однако по инвестиции в принятии полностью может сэкономить время для обслуживания приложения в будущем. Дополнительные сведения о преимуществах полностью см [изолированных приложений](http://msdn.microsoft.com/library/aa375190).  
  
 При создании собственного приложения C/C++ с помощью Visual C++, система проектов по умолчанию Visual Studio создает файл манифеста, в котором описываются зависимости приложения от библиотек Visual C++. Если все зависимости приложения имеет, то оно становится изолированное приложение, как только он будет перестроен с помощью Visual Studio. Если используются другие библиотеки приложения во время выполнения, то может потребоваться их повторное построение в качестве side-by-side сборок действий, описанных в [построение C/C++-параллельных сборок](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>См. также  
 [Концепции изолированных приложений и сборок Side-by-side](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Создание изолированных приложений и параллельных сборок C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)