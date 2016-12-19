---
title: "Добавление класса MFC | Microsoft Docs"
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
  - "vc.codewiz.classes.adding.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], добавление MFC"
  - "MFC - библиотека, классы - добавление"
ms.assetid: 9a96b67f-40bf-43d4-8872-2f8dfc5404f1
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление класса MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы добавить классы, производные от классов библиотеки Microsoft Foundation Class \(MFC\), используйте команду **Добавить класс** в меню [Окно классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  Укажите имя нового класса, выберите базовый класс и идентификатор диалогового окна, с которым он связан \(если таковое имеется\).  Мастер кодов создает файл заголовка и файл реализации и добавляет их в проект.  
  
> [!NOTE]
>  Классы MFC можно добавить в COM\-приложение ATL, если изначально [приложение создано с поддержкой MFC](../../atl/reference/mfc-support-in-atl-projects.md).  Классы MFC можно также добавить в проекты Win32 с поддержкой MFC.  
  
### Добавление класса MFC в проект  
  
1.  Щелкните имя проекта правой кнопкой мыши в окне классов.  Выберите команду **Добавить**, а затем **Добавить класс**, чтобы открыть диалоговое окно [Добавление класса](../../ide/add-class-dialog-box.md).  
  
2.  В области шаблонов выберите **Класс MFC** и нажмите кнопку **Добавить**.  
  
3.  В диалоговом окне [Мастер классов MFC](../../mfc/reference/mfc-add-class-wizard.md) определите параметры для нового класса.  
  
4.  Нажмите кнопку **Готово**, чтобы закрыть мастер и увидеть новый класс в окне классов.  Можно также просмотреть файлы, созданные мастером, в **обозревателе решений**.  
  
## См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Общие сведения о классах](../../mfc/class-library-overview.md)