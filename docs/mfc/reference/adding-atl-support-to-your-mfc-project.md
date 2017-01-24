---
title: "Добавление поддержки ATL в проект MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.adding.atl.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, проекты MFC"
  - "MFC - библиотека, поддержка ATL"
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление поддержки ATL в проект MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если приложение на базе MFC уже создано, можно легко добавить поддержку библиотеки шаблонных классов ATL посредством запуска мастера добавления поддержки ATL в проект MFC.  
  
> [!NOTE]
>  MFC и библиотеки ATL обычно не поддерживаются в выпусках Visual Studio.  
  
> [!NOTE]
>  Эта поддержка действует только для простых объектов COM, добавленных в проект исполняемого приложения MFC или библиотеки DLL.  Можно добавить другие объекты СОМ \(включая элементы управления ActiveX\) в проекты MFC, однако объекты могут работать некорректно.  
  
### Добавление поддержки ATL в проект MFC  
  
1.  В обозревателе решений щелкните правой кнопкой мыши проект, к которому нужно добавить поддержку ATL.  
  
2.  В контекстном меню выберите команду **Добавить**, а затем щелкните **Добавить класс**.  
  
3.  Выберите значок **Добавить к проекту поддержку ATL**.  
  
    > [!NOTE]
    >  Этот значок расположен в папке ATL в панели **Категории**.  
  
4.  Когда появится запрос на подтверждение, нажмите кнопку **Да**, чтобы добавить поддержку ATL.  
  
 Дополнительные сведения о том, как добавление поддержки ATL изменяет код проекта MFC, см. в разделе [Сведения о добавлении поддержки ATL мастером ATL](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)  
  
## См. также  
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление функции\-члена](../../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной\-члена](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Переопределение виртуальной функции](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)