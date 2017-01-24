---
title: "Changing a Symbol or Symbol Name (ID) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing a Symbol or Symbol Name (ID)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании нового ресурса или объекта ресурса среда разработки присваивает ему имя символа, заданное по умолчанию, например, IDD\_DIALOG1.  Чтобы изменить имя символа, заданное по умолчанию, или изменить имя любого символа, уже связанного с ресурсом, можно использовать [окно свойств](../Topic/Properties%20Window.md).  
  
### Изменение имени символа ресурса  
  
1.  Выберите нужный ресурс в [представлении ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC\-файлов, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В окне **Свойства** введите новое имя символа или выберите из списка существующих символов в поле **Идентификатор**.  
  
     При вводе нового имени символа ему автоматически присваивается значение.  
  
 Чтобы изменить имена символов, не назначенных в настоящий момент ресурсу, можно использовать [диалоговое окно "Символы ресурсов"](../windows/resource-symbols-dialog-box.md) .  Дополнительные сведения см. в статье [Изменение неназначенных символов](../Topic/Changing%20Unassigned%20Symbols.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в статье [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)