---
title: "Свойство &quot;Тип&quot; сочетания клавиш | Microsoft Docs"
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
  - "Type - свойство"
  - "VIRTKEY"
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Свойство &quot;Тип&quot; сочетания клавиш
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Свойство **Тип** сочетания клавиш позволяет определить, является ли сочетание клавиш, связанное с идентификатором ускорителя, виртуальным сочетанием клавиш или значением клавиши ASCII\/ANSI:  
  
-   Если свойство **Тип** имеет значение **ASCII**, допустимым будет только [модификатор](../windows/accelerator-modifier-property.md) "ALT" или "Отсутствует", или же сочетание клавиш должно будет включать клавишу CTRL \(чтобы задать такое сочетание, необходимо перед клавишей указать символ ^\).  
  
-   Если свойство **Тип** имеет значение **VIRTKEY**, допустимым является любое сочетание модификатора и значений клавиш.  
  
    > [!NOTE]
    >  Если необходимо ввести в таблицу сочетаний клавиш значение, которое распознавалось бы как ASCII\/ANSI, щелкните "Тип", соответствующий записи в таблице, и выберите "ASCII" в раскрывающемся списке.  Однако, если клавиша задается с помощью команды **Запись сочетания клавиш** \(в меню **Правка**\), необходимо будет изменить значение свойства **Тип** VIRTKEY на ASCII *непосредственно перед* тем, как вводить код клавиши.  
  
## Требования  
 Win32  
  
## См. также  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../Topic/Accelerator%20Editor.md)