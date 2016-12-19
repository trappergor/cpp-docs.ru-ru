---
title: "Отношение к API языка C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "книги [C++]"
  - "книги [C++], о MFC и Windows SDK"
  - "MFC [C++], API Windows"
  - "Visual C, Вызовы API Windows"
  - "Windows API [C++], и MFC"
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Отношение к API языка C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отдельная характеристика, задающей библиотеки Microsoft Foundation Class \(MFC\) друг от других библиотек классов для Windows очень точное сопоставление в API Windows, написанный в язык C.  Кроме того, можно обычно вызовы набора в библиотеку классов свободно с прямыми вызовами API Windows.  Этот прямой доступ, не означает, что классы полная замена для данного API.  Разработчики должны периодически выполнять все же прямые вызовы к некоторым функциям Windows, например [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) и [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), например.  Функция Windows создана программу\-оболочку функцией члена класса, только если очистить преимуществом методика.  
  
 Поскольку иногда нужно делать собственные вызовы функций Windows, необходимо иметь доступ к документации API Windows языка C\#.  Эта документация имеется с Microsoft Visual C\+\+.  
  
> [!NOTE]
>  Сведения о том, как работает платформа библиотеки MFC см. в разделе [Использование классов для создания приложений для Windows](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md).  
  
## См. также  
 [Общие принципы разработки классов](../mfc/general-class-design-philosophy.md)