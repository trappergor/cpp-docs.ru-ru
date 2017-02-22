---
title: "Добавление элемента управления ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "проекты ATL, добавление элементов управления"
  - "элементы управления [ATL], добавление в проекты"
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Добавление элемента управления ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот мастер используется для добавления объекта пользовательского интерфейса, поддерживающего интерфейсы всех потенциальных контейнеров.  Для поддержки этих интерфейсов проект должен быть создан как приложение ATL либо приложение MFC с поддержкой ATL.  Можно использовать [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
### Добавление в проект элемента управления ATL  
  
1.  В окне **Обозреватель решений** или [Представление классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой мыши имя проекта, в который нужно добавить простой объект ATL.  
  
2.  Выберите в контекстном меню команду **Добавить**, а затем **Добавить класс**.  
  
3.  В области "Шаблоны" диалогового окна [Добавление класса](../../ide/add-class-dialog-box.md) щелкните **Элемент управления ATL**, а затем нажмите кнопку **Добавить**, чтобы открылся [Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).  
  
 Используя **Мастер элементов управления ATL**, можно создавать три типа элементов управления:  
  
-   Стандартный элемент управления  
  
-   Составной элемент управления  
  
-   Элемент управления DHTML  
  
 Кроме того, вы можете уменьшить размер элемента управления и удалить интерфейсы, не используемые большинством контейнеров, выбрав **Минимальный элемент управления** на странице **Параметры** мастера.  
  
## См. также  
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATLFire Sample](http://msdn.microsoft.com/ru-ru/5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)