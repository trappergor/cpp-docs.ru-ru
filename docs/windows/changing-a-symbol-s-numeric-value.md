---
title: "Changing a Symbol&#39;s Numeric Value | Microsoft Docs"
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
  - "vc.editors.symbol.changing.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric values"
  - "symbols, numeric values"
  - "numeric values, changing symbols"
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing a Symbol&#39;s Numeric Value
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для символов, связанных с одиночным ресурсом, можно использовать [окно свойств](../Topic/Properties%20Window.md), чтобы изменить значение символа.  Чтобы изменить значения символов, не назначенных в настоящий момент ресурсу, можно использовать [диалоговое окно "Символы ресурсов"](../windows/resource-symbols-dialog-box.md) .  Дополнительные сведения см. в статье [Изменение неназначенных символов](../Topic/Changing%20Unassigned%20Symbols.md).  
  
### Изменение значения символа, назначенного одному ресурсу или объекту  
  
1.  Выберите нужный ресурс в [представлении ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC\-файлов, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В окне **Свойства** введите имя символа, за ним знак равенства и целое число в поле **Идентификатор**, например:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 Новое значение будет сохранено в файле символов заголовков при очередном сохранении проекта.  В поле "Идентификатор" будет отображаться только имя символа. Знак равенства и значение не будут отображаться после проверки.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Symbol Value Restrictions](../Topic/Symbol%20Value%20Restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)