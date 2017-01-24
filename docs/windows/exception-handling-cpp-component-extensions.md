---
title: "Обработка исключений (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++"
  - "Exception - класс, управляемые приложения"
  - "обработка исключений"
  - "обработка исключений, типы"
  - "управляемые исключения"
  - "структурированная обработка исключений, управляемые исключения"
  - "System::Exception - класс (в управляемых приложениях)"
ms.assetid: ccb11fe8-6938-41ac-b477-a183e85865b9
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка исключений (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложения, скомпилированные с параметром компилятора **\/ZW** или параметром компилятора **\/clr**, используют *исключения* для обработки непредвиденных ошибок во время выполнения программы.  В следующих разделах обсуждается обработка исключений в приложениях C\+\+\/CX или C\+\+\/CLI.  
  
## В этом подразделе  
 [Основные принципы использования управляемых исключений](../dotnet/basic-concepts-in-using-managed-exceptions.md)  
 Описывает создание исключений и использование блоков `try`\/`catch`.  
  
 [Различия в поведении при обработке исключений](../dotnet/differences-in-exception-handling-behavior-under-clr.md)  
 Обсуждаются отличия от стандартного поведения обработки исключений C\+\+.  
  
 [finally](../dotnet/finally.md)  
 Описание использования ключевого слова finally.  
  
 [Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)  
 Демонстрирует, как можно захватить необработанные исключения.  
  
 [Практическое руководство. Исключения в машинном коде, создаваемые MSIL](../dotnet/how-to-catch-exceptions-in-native-code-thrown-from-msil.md)  
 Описывает способы перехвата исключений CLR и C\+\+ в машинном коде.  
  
 [Практическое руководство. Определение и установка глобального обработчика исключений](../dotnet/how-to-define-and-install-a-global-exception-handler.md)  
 Демонстрируется, как перехватить все необработанные исключения.  
  
## Связанные подразделы  
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)  
 Описывает обработку исключений в C\+\+.  
  
## См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)