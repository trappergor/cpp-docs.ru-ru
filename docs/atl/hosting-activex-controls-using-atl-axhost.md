---
title: "Hosting ActiveX Controls Using ATL AXHost | Microsoft Docs"
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
  - "элементы управления ActiveX [C++], размещение"
  - "AXHost method"
  - "Calendar control (ActiveX)"
  - "Calendar control (ActiveX), hosting with ATL AXHost"
  - "CAxWindow2T class"
  - "размещение элементов управления ActiveX"
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Hosting ActiveX Controls Using ATL AXHost
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пример в этом разделе показано, как создать AXHost и размещение элементов управления ActiveX с помощью различных функций библиотеки ATL.  Кроме того, показано, как получить доступ к элементу управления и утонуть события \(с использованием [IDispEventImpl](../atl/reference/idispeventimpl-class.md)\) из элемента управления, который размещается.  Пример размещение элемент управления "Календарь" в главном окне или в дочернем окне.  
  
 Обратите внимание `USE_METHOD` определение символа.  Можно изменить значение этого символа в зависимости от 1 до 8.  Значение символа определяет, как элемент управления будет создать.  
  
-   Для ровн\- нумерованных значений `USE_METHOD`, вызова для создания подклассы узла окно и новообращенные его в узел элемента управления.  Для нечетн\- нумерованных значений код создает дочернее окно, которое выступает в роли основного приложения.  
  
-   Для значений `USE_METHOD` между 1 и 4, доступ к элементу управления и тонуть событий выполняются в вызов, который также создает основное приложение.  Значения от 5 до 8, выполняющих запрос к основному приложению интерфейсов и закрепляют приемник.  
  
 Ниже приводится сводка:  
  
|USE\_METHOD|Основное приложение|Контролируйте доступ и тонуть события|Функция которые представлены|  
|-----------------|-------------------------|-------------------------------------------|----------------------------------|  
|1|Дочернее окно|Один этап|CreateControlLicEx|  
|2|Главное окно|Один этап|AtlAxCreateControlLicEx|  
|3|Дочернее окно|Один этап|CreateControlEx|  
|4|Главное окно|Один этап|AtlAxCreateControlEx|  
|5|Дочернее окно|Множественные инструкции|CreateControlLic|  
|6|Главное окно|Множественные инструкции|AtlAxCreateControlLic|  
|7|Дочернее окно|Множественные инструкции|CreateControl|  
|8|Главное окно|Множественные инструкции|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/CPP/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](../Topic/AtlAxCreateControl.md)   
 [AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)   
 [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)   
 [AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)   
 [CAxWindow2T Class](../Topic/CAxWindow2T%20Class.md)   
 [IAxWinHostWindowLic Interface](../atl/reference/iaxwinhostwindowlic-interface.md)