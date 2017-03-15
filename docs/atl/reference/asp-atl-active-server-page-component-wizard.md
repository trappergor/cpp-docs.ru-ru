---
title: "ASP, мастер компонентов страницы активного сервера ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.asp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Мастер компонентов страницы активного сервера ATL, ASP"
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ASP, мастер компонентов страницы активного сервера ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используйте мастер компонентов Active Server Pages библиотеки ATL для указания дополнительных параметров для обработки информации и состояний, связанных с компонентами ASP.  
  
 **Дополнительные методы**  
 Добавляют в объект дополнительные ASP методы **OnStartPage** и **OnEndPage**.  Данные параметры можно задать для любых внутренних объектов ASP.  По умолчанию они выбраны.  
  
-   **OnStartPage\/OnEndPage** [OnStartPage](https://msdn.microsoft.com/en-us/library/ms691624.aspx) вызывается при попытке скрипта получить доступ к объекту.  **OnEndPage** вызывается, когда объект заканчивает обработку скрипта.  
  
 **Встроенные объект**  
 Для задания встроенных объектов ASP, необходимо выбрать параметр **OnStartPage\/OnEndPage**.  
  
|Параметр|Описание|  
|--------------|--------------|  
|**Запрос**|Предоставляет доступ к встроенному объекту **Request**.  Объект Request используется для передачи HTTP\-запроса.|  
|**Ответ**|Предоставляет доступ к встроенному объекту ASP **Response**.  В ответ на запрос, объект Response передает данные в браузер для их отображения пользователю.|  
|**Сеанс;**|Предоставляет доступ к встроенному объекту **Session**.  Объект **Session** содержит данные о текущем сеансе работы пользователя, хранит и получает данные о его состоянии.|  
|**Приложение**|Предоставляет доступ к встроенному объекту **Application**.  Объект **Application** управляет общим состоянием множества объектов ASP.|  
|**Server**|Предоставляет доступ к встроенному объекту **Server**.  Объект **Server** позволяет создавать другие объекты ASP.|  
  
## См. также  
 [мастер ASP\-компонентов библиотеки ATL](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)