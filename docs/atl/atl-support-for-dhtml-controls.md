---
title: "Поддержка элементов управления DHTML в ATL | Microsoft Docs"
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
  - "элементы управления DHTML"
  - "элементы управления DHTML, поддержка ATL"
  - "элементы управления HTML, поддержка ATL"
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Поддержка элементов управления DHTML в ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью библиотеки ATL можно создать элемент управления с возможностью динамического HTML \(DHTML\).  Элемент управления DHTML библиотеки ATL:  
  
-   Хозяйничает элемент управления WebBrowser.  
  
-   Определяет, используя HTML, интерфейс пользователя управления DHTML.  
  
-   Объект WebBrowser и обращается к его методам через интерфейс, [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx).  
  
-   Связь элементов управления между кодом C\+\+ и HTML.  
  
 Элемент управления DHTML аналогично любому другому элементу управления библиотеки ATL, за исключением того, что элемент управления DHTML включает дополнительный интерфейс диспетчеризации.  См. рисунок в [Идентификация элементов проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) для иллюстрации интерфейсов, предоставляемых в DHTML запроектировать по умолчанию.  
  
 Можно просмотреть элемент управления DHTML библиотеки ATL в веб\-браузере или другом контейнере, например тестовый контейнер элементов управления ActiveX.  
  
## В этом подразделе  
 [Идентификация элементов проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Описывает элементы проекта элемента управления DHTML.  
  
 [Вызов кода C\+\+ из DHTML](../Topic/Calling%20C++%20Code%20from%20DHTML.md)  
 Пример вызова кода C\+\+ из элемента управления DHTML.  
  
 [Создание элемента управления DHTML библиотеки ATL](../atl/creating-an-atl-dhtml-control.md)  
 Содержит инструкции по созданию элемента управления DHTML.  
  
 [Тестирование элемента управления DHTML библиотеки ATL](../atl/testing-the-atl-dhtml-control.md)  
 Показано, как выполнить построение и тестирование исходный проект элемента управления DHTML.  
  
 [Изменение элемент управления DHTML библиотеки ATL](../atl/modifying-the-atl-dhtml-control.md)  
 Показано, как добавить некоторые функциональные возможности к элементу управления.  
  
 [Тестирование измененное элемент управления DHTML библиотеки ATL](../atl/testing-the-modified-atl-dhtml-control.md)  
 Показано, как выполнить построение и тестирование функциональные возможности элемента управления, добавленную.  
  
## Связанные подразделы  
 [Библиотека ATL](../atl/active-template-library-atl-concepts.md)  
 Содержит ссылки на концептуальные разделы о том, как запрограммировать с помощью библиотека шаблонных классов ATL.