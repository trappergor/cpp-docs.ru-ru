---
title: "Исключение при обработке (расширения компонентов C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- structured exception handling, managed exceptions
- Exception class, managed applications
- exception handling
- C++ exception handling
- exception handling, types of
- managed exceptions
- System::Exception class in managed applications
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d6f43bd1953cc13189f53d97090d3913a49072ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling--c-component-extensions"></a>Обработка исключений (расширения компонентов C++)
Приложения, скомпилированные с **/ZW** параметр компилятора или **/CLR** используются *исключения* для обработки непредвиденных ошибок во время выполнения программы. В следующих разделах рассматривается обработка исключений в приложениях C++/CX и C++/CLI.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Основные принципы использования управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md)  
 Описывает создание исключений и использование `try` / `catch` блоков.  
  
 [Различия в поведении в/CLR при обработке исключений](../dotnet/differences-in-exception-handling-behavior-under-clr.md)  
 Рассматриваются отличия от стандартного поведения обработки исключений C++.  
  
 [finally](../dotnet/finally.md)  
 Описывается использование ключевого слова finally.  
  
 [Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)  
 Демонстрируется захват необработанных исключений.  
  
 [Практическое руководство. Исключения в машинном коде, создаваемые MSIL](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)  
 Описывается перехват исключений CLR и C++ в машинном коде.  
  
 [Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)  
 Демонстрируется перехват всех необработанных исключений.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)  
 Описывается обработка исключений в C++.  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)