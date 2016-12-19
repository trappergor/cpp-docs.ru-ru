---
title: "Какие классы и функции MFC не могут использоваться в библиотеке DLL MFC? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL-библиотеки [C++], MFC - библиотека"
  - "DLL-библиотеки [C++], ограничения"
  - "библиотеки DLL MFC [C++], ограничения"
ms.assetid: 18e2f1cb-4f72-4d3a-a951-3488208872c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Какие классы и функции MFC не могут использоваться в библиотеке DLL MFC?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки расширения DLL используют класс клиентского приложения, производный от класса `CWinApp`.  Они не могут иметь собственный класс, производный от `CWinApp`.  
  
 Стандартные библиотеки DLL, как и приложения MFC, должны содержать класс, производный от `CWinApp`, и один объект этого класса.  В отличие от объекта класса `CWinApp` приложения объект класса `CWinApp` библиотеки DLL не имеет основного конвейера сообщений.  
  
 Обратите внимание, что поскольку механизм `CWinApp::Run` не применяется для библиотек DLL, приложение имеет основной конвейер сообщений.  Если библиотека DLL открывает безрежимные диалоговые окна или имеет собственный фрейм окна, то в основном цикле сообщений приложения должна вызываться подпрограмма, экспортируемая библиотекой DLL, которая, в свою очередь, вызывает функцию\-член `CWinApp::PreTranslateMessage` объекта приложения библиотеки DLL.  
  
## См. также  
 [Вопросы и ответы по библиотекам DLL](../build/dll-frequently-asked-questions.md)