---
title: "Changing the Properties of Multiple Accelerator Keys | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "keyboard shortcuts [C++], property changing"
  - "accelerator tables [C++], changing properties"
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Changing the Properties of Multiple Accelerator Keys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Изменение свойств для нескольких сочетаний клавиш  
  
1.  Откройте таблицу сочетаний клавиш, дважды щелкнув соответствующий значок в [представлении ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Чтобы выделить несколько сочетаний клавиш, свойства которых необходимо изменить, прижмите клавишу **CTRL** и щелкните последовательно все нужные сочетания.  
  
3.  Перейдите к [окну свойств](../Topic/Properties%20Window.md) и введите значения, которые должны быть одинаковыми у всех сочетаний.  
  
    > [!NOTE]
    >  Каждое значение модификатора отображается в окне свойств как логическое значение.  Если [значение модификатора](../windows/accelerator-modifier-property.md) изменить в окне свойств, в таблице сочетаний клавиш новый модификатор будет интерпретироваться как дополнение к ранее использовавшимся модификаторам.  В связи с этим в процессе установки значений модификатора необходимо будет задать значения всех модификаторов, чтобы убедиться, что для всех сочетаний клавиш заданы одинаковые параметры.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Editing Accelerator Tables](../windows/editing-accelerator-tables.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)