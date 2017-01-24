---
title: "Классы-оболочки | Microsoft Docs"
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
  - "элементы управления ActiveX [C++], классы-оболочки"
  - "привязка данных [C++], элементы управления ActiveX"
  - "классы-оболочки [C++], элементы управления ActiveX"
ms.assetid: ebbc17b9-cc1b-4c29-afa9-da7f9511876e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы-оболочки
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если вставить [элемент управления](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) в проект Visual C\+\+, классы\-оболочки не будут добавлены по умолчанию.  Тем не менее, если потребуется [изменить поведение элементов управления](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md), классы\-оболочки можно прописать для элемента управления.  В зависимости от того, как планируется управлять элементами управления программно, потребуется написать один или несколько классов\-оболочек.  
  
 Класс\-оболочка доступен для каждого из компонентных классов в TLB\-файле библиотеки элементов управления.  Класс\-оболочка элемента управления должен иметь имя элемента управления с префиксом "С".  
  
 Дополнительные сведения о функциях класса\-оболочки см. в описании объектной модели для базовой технологии элементов управления.  
  
 Использование [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) также требует применения классов\-оболочек, так как возвращаемое значение должно быть приведено к классу элемента управления.  Примеры.  
  
```  
CDBList* pDBList = 0;  
pDBList = static_cast<CDBList*>(GetDlgItem(IDC_DBLIST));  
```  
  
 Считывание созданного IDL\-файла дает возможность определить какие свойства, методы и события предоставляются элементом управления, а также увидеть объявления функций и методов доступа напрямую.  Дополнительные сведения см. в разделе [Программа просмотра объектов OLE\/COM](../Topic/Using%20the%20OLE-COM%20Object%20Viewer.md).  
  
## См. также  
 [Использование элементов управления ActiveX](../Topic/Using%20ActiveX%20Controls.md)   
 [Изменение поведения элемента управления во время выполнения](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)