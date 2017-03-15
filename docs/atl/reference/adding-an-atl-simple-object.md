---
title: "Добавление простого объекта ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.classes.adding.atl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, добавление объектов"
  - "ATL - библиотека, простые объекты"
  - "объекты [ATL]"
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Добавление простого объекта ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы добавить в проект объект библиотеки шаблонных классов \(ATL\), проект должен быть создан как приложение ATL или как приложение MFC, содержащее поддержку ATL.  Можно использовать [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 COM\-интерфейсы для нового объекта ATL можно определить при создании объекта или добавить их позднее с помощью команды [Реализовать интерфейс](../Topic/Implement%20Interface%20Wizard.md) из контекстного меню окна классов.  
  
### Добавление простого объекта ATL в проект ATL COM  
  
1.  В окне **Обозреватель решений** или [Представление классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой мыши имя проекта, в который нужно добавить простой объект ATL.  
  
2.  Выберите в контекстном меню команду **Добавить**, а затем **Добавить класс**.  
  
3.  В области шаблонов диалогового окна [Добавление класса](../../ide/add-class-dialog-box.md) щелкните **Простой объект ATL**, а затем щелкните **Открыть**, чтобы отобразился [Мастер простых объектов ATL](../../atl/reference/atl-simple-object-wizard.md).  
  
4.  В мастере простых объектов ATL на странице [Параметры](../../atl/reference/options-atl-simple-object-wizard.md) задайте дополнительные параметры для проекта.  
  
5.  Нажмите кнопку **Готово**, чтобы добавить объект в проект.  
  
## См. также  
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление нового интерфейса в проект ATL](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md)   
 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md)   
 [Добавление метода](../../ide/adding-a-method-visual-cpp.md)   
 [Класс MFC](../../mfc/reference/adding-an-mfc-class.md)   
 [Добавление универсального класса C\+\+](../../ide/adding-a-generic-cpp-class.md)