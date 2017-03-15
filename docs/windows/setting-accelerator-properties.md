---
title: "Задание свойств сочетаний клавиш | Microsoft Docs"
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
  - "свойства сочетаний клавиш"
  - "свойства [C++], свойства сочетаний клавиш"
  - "Type - свойство"
  - "свойство Key"
  - "Modifier - свойство"
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Задание свойств сочетаний клавиш
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В Visual C++ .NET, можно задать свойства сочетаний клавиш в [окно свойств](../Topic/Properties%20Window.md) в любое время. Можно также использовать редактор сочетаний клавиш для изменения свойств сочетаний клавиш в таблице сочетаний клавиш. Изменения, внесенные с помощью окна свойств или редактора сочетаний клавиш, имеют один и тот же результат: изменения немедленно отражаются в таблице сочетаний клавиш.  
  
 Существует три свойства для каждого сочетания [идентификатор](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-    [Свойство "модификатор"](../windows/accelerator-modifier-property.md) задает сочетания клавиш для быстрого вызова элемента управления.  
  
    > [!NOTE]
    >  В окне свойств это свойство появляется как три отдельных логических свойства, каждым из которых можно управлять независимо: Alt, Ctrl или Shift.  
  
-    [Ключевое свойство](../Topic/Accelerator%20Key%20Property.md) задает фактическую клавишу, используемую в качестве ускорителя.  
  
-    [Свойство типа](../windows/accelerator-type-property.md) определяет, является ли ключ интерпретируется как виртуальный (VIRTKEY) или ASCII и ANSI.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)  *Руководства разработчика .NET Framework* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Стандартные сочетания клавиш](../windows/predefined-accelerator-keys.md)   
 [Редакторы ресурсов](../mfc/resource-editors.md)   
 [Редактор сочетаний клавиш](../Topic/Accelerator%20Editor.md)