---
title: "Symbols: Resource Identifiers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.identifiers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, resource identifiers"
  - "symbols, creating"
  - "resource symbols"
  - "symbols, editing"
  - "resource editors, resource symbols"
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Symbols: Resource Identifiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Символ представляет собой идентификатор ресурса, состоящий из двух частей: текстовой строки \(имени символа\), сопоставленной с целочисленным значением \(значением символа\). Например:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 Под идентификаторами, как правило, подразумевают имена символов.  
  
 Символы позволяют описательно ссылаться на ресурсы и объекты пользовательского интерфейса как в исходном коде, так и во время работы с ресурсами в редакторах. Диалоговое окно [Символы ресурсов](../windows/viewing-resource-symbols.md) представляет собой удобный инструмент, позволяющий выполнять с символами разные действия.  
  
 В процессе создания ресурса или объекта ресурса [редакторы ресурсов](../mfc/resource-editors.md) присваивают ресурсу имя по умолчанию, например `IDC_RADIO1`, а также присваивают ему значение. Определение, состоящее из имени и значения, хранится в файле Resource.h.  
  
> [!NOTE]
>  В процессе копирования ресурсов или объектов ресурсов из одного RC\-файла в другой Visual C\+\+ может изменить значение или имя и значение символа копируемого ресурса во избежание конфликтов с именами и значениями символов в существующем файле.  
  
 Соответственно тому, как увеличивается размер приложения и сложность его структуры, растет количество ресурсов и символов. Отслеживание большого количества символов, разбросанных по нескольким файлам, может оказаться трудоемкой задачей. Диалоговое окно [Символы ресурсов](../windows/resource-symbols-dialog-box.md) упрощает управление символами, позволяя выполнять следующие действия:  
  
-   [просмотр символов ресурсов;](../windows/viewing-resource-symbols.md)  
  
-   [создание символов;](../windows/creating-new-symbols.md)  
  
-   [изменение неназначенных символов;](../Topic/Changing%20Unassigned%20Symbols.md)  
  
-   [удаление неназначенных символов;](../windows/deleting-unassigned-symbols.md)  
  
-   [открытие редактора ресурсов для заданного символа;](../Topic/Opening%20the%20Resource%20Editor%20for%20a%20Given%20Symbol.md)  
  
-   [изменение символа или символьного имени \(идентификатора\);](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
-   [изменение числового значения символа;](../windows/changing-a-symbol-s-numeric-value.md)  
  
-   [изменение имен файлов заголовков символов;](../windows/changing-the-names-of-symbol-header-files.md)  
  
-   [включение общих \(доступных только для чтения\) или вычисляемых символов;](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
-   [просмотр предопределенных идентификаторов символов.](../windows/predefined-symbol-ids.md)  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделах [Пошаговое руководство. Локализация Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 Win32  
  
## См. также  
 [How to: Search for Symbols in Resources](../windows/how-to-search-for-symbols-in-resources.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)