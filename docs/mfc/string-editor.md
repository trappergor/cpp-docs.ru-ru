---
title: "String Editor | Microsoft Docs"
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
  - "vc.editors.string.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "String editor"
  - "string tables"
  - "string tables, String editor"
  - "string editing"
  - "string editing, string tables"
  - "resource editors, String editor"
  - "strings [C++], editing"
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# String Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Таблица строк — это ресурс Windows, содержащий список идентификаторов, значений и заголовков для всех строк в приложении. Например, в таблице строк могут содержаться подсказки, выводимые в строке состояния.  
  
 В процессе разработки приложения можно использовать несколько таблиц строк для разных языков и ситуаций. Однако исполняемый модуль имеет только одну таблицу строк. Работающее приложение может ссылаться на несколько таблиц строк, если они помещены в разные библиотеки DLL.  
  
 Таблицы строк упрощают локализацию приложения на разные языки. Если все строки находятся в таблице строк, вы можете локализовать приложение, переведя строки \(и другие ресурсы\) и не меняя исходный код. Обычно это удобнее, чем вручную искать и заменять различные строки в исходных файлах.  
  
 С помощью редактора можно выполнять следующие действия:  
  
-   [искать одну или несколько строк](../mfc/finding-a-string.md);  
  
-   быстро [вставлять новые записи](../mfc/adding-or-deleting-a-string.md) в таблицу строк;  
  
-   [перемещать строку из одного файла ресурсов в другой;](../mfc/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [редактировать свойства ID, Value и Caption на месте](../mfc/changing-the-properties-of-a-string.md) и немедленно просматривать изменения;  
  
-   [изменять свойство заголовка для нескольких строк;](../mfc/changing-the-caption-property-of-multiple-strings.md)  
  
-   [добавлять форматирование или специальные символы в строку.](../mfc/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows не разрешает создавать пустые таблицы строк. Если вы создадите таблицу строк, не содержащую записей, она будет автоматически удалена при сохранении файла ресурсов.  
  
 Сведения о добавлении ресурсов в управляемые проекты \(предназначенные для среды CLR\) см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [Resource Editors](../mfc/resource-editors.md)   
 [Строки](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Сведения о строках](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)