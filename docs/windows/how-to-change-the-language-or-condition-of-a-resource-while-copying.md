---
title: "How to: Change the Language or Condition of a Resource While Copying | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resvw.resource.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Language property"
  - "condition property of resource"
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# How to: Change the Language or Condition of a Resource While Copying
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Во время копирования ресурса можно изменить его свойство "язык" и \(или\) "условие".  
  
-   Язык ресурса определяет собственно язык ресурса.  Это значение используется функцией [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) для идентификации ресурса, который требуется найти.  \(Однако ресурсы могут иметь отличия, характерные для каждого языка, которые не связаны с текстом, например, сочетания клавиш, которые работают только на японской клавиатуре или растровые изображения, подходящие только для китайских локализованных сборок, и т. д.\)  
  
-   Условие ресурса — это определенный символ, задающий условие, при котором будет использоваться конкретная копия ресурса.  
  
 Язык и условие ресурса отображаются в окне рабочей области в скобках после имени ресурса.  В этом примере ресурс с именем IDD\_AboutBox использует финский язык и его условие имеет значение XX33.  
  
```  
IDD_AboutBox (Finnish – XX33)  
```  
  
### Копирование существующего ресурса и изменение его языка или условия  
  
1.  В RC\-файле или в окне [Представление ресурсов](../windows/resource-view-window.md) щелкните правой кнопкой мыши ресурс, который нужно скопировать.  
  
2.  Выберите в контекстном меню команду **Вставить копию**.  
  
3.  В диалоговом окне **Вставка копии ресурса**:  
  
    -   В списке **Язык** выберите требуемый язык.  
  
    -   В поле **Условие** введите требуемое условие.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [How to: Copy Resources](../windows/how-to-copy-resources.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)