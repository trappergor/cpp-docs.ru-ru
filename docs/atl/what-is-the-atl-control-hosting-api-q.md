---
title: "What Is the ATL Control-Hosting API? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "API - интерфейсы [C++], размещение"
  - "control-hosting API"
  - "элементы управления [ATL], хост-API"
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 15
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# What Is the ATL Control-Hosting API?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Элемент управления\- размещения API библиотеки ATL набор функций, который разрешает любое окно для использования в качестве контейнера элемента управления ActiveX.  Эти функции можно статически или динамически связывать в проект, поскольку они доступны как исходный код, предоставленный ATL90.dll.  Элемент управления\- функции размещения перечислены в таблице ниже.  
  
|Функция|Описание|  
|-------------|--------------|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|Создает объект узла, он соединяется с предоставленным окно вложение, а затем существующий элемент управления.|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|Создает объект узла, он соединяется с предоставленным окно, а затем загружает элемент управления.|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|Создает лицензированное элемент управления ActiveX, инициализирует и размещение его в определенном окне, аналогично [AtlAxCreateControl](../Topic/AtlAxCreateControl.md).|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|Создает объект узла, он соединяется с предоставленным окно, а затем загружает элемент управления также позволяет приемники событий, которые необходимо настроить.|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|Создает лицензированное элемент управления ActiveX, инициализирует и размещение его в определенном окне, аналогично [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md).|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|Создает безрежимное диалоговое окно из ресурса диалогового окна, и возвращает дескриптор окна.|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|Создание модального диалогового окна из ресурса диалогового окна.|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|Получает указатель интерфейса **IUnknown** элемента управления, который хозяйничают в окне.|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|Получает указатель интерфейса **IUnknown** подключенного объекта основного приложения в окно.|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|Инициализирует элемент управления\- код размещения.|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|Uninitializes код элемента управления\- размещения.|  
  
 Параметры `HWND` в первых 3 функциях должны быть существующим окном \(почти\) любого типа.  При вызове любой из этих функций явно 3 \(обычно вы не сможете\), то не следует передавать дескриптор окна, которое уже действует как узел \(если это сделать, то не освобождается существующий объект узла\).  
  
 Первый вызов 7 функций [AtlAxWinInit](../Topic/AtlAxWinInit.md) неявно.  
  
> [!NOTE]
>  Элемент управления\- API размещения основой форм поддержки библиотеки ATL для включения элемента управления ActiveX.  Однако обычно меньшяя необходимость вызова этих функций напрямую, если необходимо воспользоваться преимуществами или выполняют полную использование класс\-оболочек библиотеки ATL.  Дополнительные сведения см. в разделе [Библиотека ATL, который классифицирует облегчает вложенность элемент управления ActiveX?](../atl/which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)