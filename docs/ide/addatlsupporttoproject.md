---
title: "AddATLSupportToProject | Microsoft Docs"
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
  - "AddATLSupportToProject - метод"
ms.assetid: 26708f22-1e9b-4432-83b2-ed94c765b753
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# AddATLSupportToProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавляет поддержку ATL в проект MFC.  
  
## Синтаксис  
  
```  
  
      function AddATLSupportToProject(   
   oProj   
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
## Возвращаемое значение  
 **true**, если поддержка ATL успешно добавлена в проект MFC.  
  
## Заметки  
 Эта функция используется для добавления поддержки ATL в проект MFC, созданный мастером.  
  
 Мастер отображает диалоговое окно, предлагающее подтвердить добавление поддержки ATL в проект MFC.  После подтверждения мастер проверяет, не добавлена ли уже такая поддержка, и добавляет все необходимые GUID, шаблоны, заголовки и дополнительную функциональность для того, чтобы созданный мастером проект MFC поддерживал ATL.  
  
## Пример  
  
```  
var oCM = selProj.CodeModel;  
var L_TRANSACTION_Text = "Add ATL Support To Project";  
oCM.StartTransaction(L_TRANSACTION_Text);  
var bRet = AddATLSupportToProject(selProj);  
if (bRet)  
   oCM.CommitTransaction();  
else  
   oCM.AbortTransaction();  
return bRet;  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [Функция CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../Topic/IsMFCProject.md)   
 [Введение в ATL](../Topic/Introduction%20to%20ATL.md)