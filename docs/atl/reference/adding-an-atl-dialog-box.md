---
title: "Adding an ATL Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, добавление диалоговых ресурсов"
  - "диалоговые окна, ATL - библиотека"
  - "диалоговые окна MFC, диалоговые окна ATL"
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding an ATL Dialog Box
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы в проект можно было добавить диалоговое окно ATL, он должен представлять собой проект ATL или проект MFC с поддержкой ATL.  Можно использовать [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 По умолчанию мастер диалоговых окон ATL реализует диалоговое окно, производное от [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md).  Этот класс поддерживает размещение элементов управления ActiveX и Windows.  Если вы хотите избежать накладных расходов, связанных с поддержкой элементов управления ActiveX, после создания кода мастером замените все вхождения `CAxDialogImpl` либо [CSimpleDialog](../../atl/reference/csimpledialog-class.md), либо [CDialogImpl](../Topic/CDialogImpl%20Class.md) в качестве базового класса.  
  
> [!NOTE]
>  `CSimpleDialog` создает только модальные диалоговые окна, поддерживающие исключительно общие элементы управления Windows.  `CDialogImpl` создает как модальные, так и немодальные диалоговые окна.  
  
### Добавление в проект ресурса диалогового окна ATL  
  
1.  Создайте проект ATL с помощью [мастера проектов ATL](../Topic/ATL%20Project%20Wizard.md).  
  
2.  В [окне классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой мыши имя проекта и выберите в контекстном меню команду **Добавить**.  Выберите команду **Добавить класс**.  
  
3.  В области "Шаблоны" диалогового окна [Добавление класса](../../ide/add-class-dialog-box.md) щелкните **Диалоговое окно ATL**.  Нажмите кнопку **Открыть**, чтобы открылся [мастер диалоговых окон ATL](../../atl/reference/atl-dialog-wizard.md).  
  
 Дополнительные сведения см. в разделе [Реализация диалогового окна](../../atl/implementing-a-dialog-box.md).  
  
## См. также  
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Классы окон](../Topic/ATL%20Window%20Classes.md)   
 [Message Maps](../../atl/message-maps-atl.md)