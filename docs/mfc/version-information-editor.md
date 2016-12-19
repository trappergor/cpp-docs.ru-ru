---
title: "Version Information Editor | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.version.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Version Information editor, about Version Information editor"
  - "editors, Version Information"
  - "resource editors, Version Information editor"
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Version Information Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сведения о версии включают идентификационные данные о компании и продукте, номер версии продукта и уведомление об авторских правах и товарных знаках. С помощью редактора сведений о версии можно создавать и поддерживать эти данные, которые хранятся в ресурсе сведений о версии. Ресурс сведений о версии не является обязательным для приложения, но он удобен для сбора сведений, позволяющих идентифицировать приложение. Сведения о версии также используются API\-интерфейсами настройки.  
  
 Ресурс сведений о версии содержит верхний блок и один или несколько нижних блоков: один блок фиксированных сведений вверху и один или несколько блоков сведений о версии внизу \(для других языков или кодировок\). Верхний блок содержит как редактируемые числовые поля, так и раскрывающиеся списки с вариантами для выбора. Нижние блоки содержат только редактируемые текстовые поля.  
  
> [!NOTE]
>  Стандарт Windows разрешает наличие только одного ресурса сведений о версии, который называется VS\_VERSION\_INFO.  
  
 Редактор сведений о версии позволяет делать следующее:  
  
-   [изменять строку в ресурсе сведений о версии;](../mfc/editing-a-string-in-a-version-information-resource.md)  
  
-   [добавлять сведения о версии для другого языка \(новый блок сведений о версии\);](../mfc/adding-version-information-for-another-language.md)  
  
-   [удалять блок сведений о версии;](../mfc/deleting-a-version-information-block.md)  
  
-   [получать доступ к сведениям о версии из создаваемой программы.](../mfc/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  При использовании редактора сведений о версии во многих случаях можно щелкнуть правой кнопкой мыши, чтобы открыть контекстное меню связанных с ресурсом команд. Например, если щелкнуть, когда указатель находится на заголовке блока, контекстное меню будет содержать команды "Создать блок сведений о версии" и "Удалить блок сведений о версии".  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Resource Editors](../mfc/resource-editors.md)   
 [Меню и другие ресурсы](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)