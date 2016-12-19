---
title: "Добавление ASP-компонента библиотеки ATL | Microsoft Docs"
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
  - "компоненты ASP"
  - "компоненты ASP, adding"
  - "компоненты ATL ASP"
  - "ATL - библиотека, компоненты ASP"
ms.assetid: 7be2204c-6e58-4099-8892-001b848c8987
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление ASP-компонента библиотеки ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Чтобы добавить в проект объект библиотеки шаблонных классов ATL, проект должен быть создан как COM\-приложение ATL или как приложение MFC, поддерживающее ATL.  Приложение ATL можно создать с помощью [мастера проектов ATL](../Topic/ATL%20Project%20Wizard.md) или выбрать пункт **Добавить поддержку ATL в MFC** в диалоговом окне [Добавление класса](../../ide/add-class-dialog-box.md), или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 ASP\-компоненты являются частью архитектуры служб IIS, которая предоставляет следующие дополнительные возможности для веб\-разработки:  
  
-   ASP\-компоненты можно внедрять в HTML\-страницы для создания динамического не зависящего от браузера содержимого;  
  
-   ASP\-страницы можно использовать для предоставления возможности стандартизованного подключения к базам данных;  
  
-   также можно использовать функции обработки ошибок ASP для веб\-приложений.  
  
### Добавление в проект ASP\-компонента ATL  
  
1.  В окне **Обозреватель решений** или [Представление классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой имя проекта, в который необходимо добавить ASP\-компонент библиотеки ATL.  
  
2.  Выберите в контекстном меню команду **Добавить**, а затем **Добавить класс**.  
  
3.  В области "Шаблоны" диалогового окна [Добавление класса](../../ide/add-class-dialog-box.md) щелкните **ASP\-компонент ATL**, а затем нажмите кнопку **Открыть**, чтобы открылся [Мастер ASP\-компонентов библиотеки ATL](../../atl/reference/atl-active-server-page-component-wizard.md).  
  
## См. также  
 [Добавление класса](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [Добавление нового интерфейса в проект ATL](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md)   
 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md)   
 [Добавление метода](../../ide/adding-a-method-visual-cpp.md)   
 [Класс MFC](../../mfc/reference/adding-an-mfc-class.md)   
 [Добавление универсального класса C\+\+](../../ide/adding-a-generic-cpp-class.md)