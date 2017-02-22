---
title: "Specifying Property Pages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISpecifyPropertyPages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages method"
  - "страницы свойств, определение"
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Specifying Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При создании элемента управления ActiveX, часто требуется связать его с помощью страниц свойств, которые могут использоваться для задания свойства элемента управления.  Контейнеры элементов управления используют интерфейс **ISpecifyPropertyPages** чтобы выяснить, страницы свойств могут использоваться для задания свойства элемента управления.  Необходимо будет реализовать этот интерфейс на элементе управления.  
  
 Для реализации **ISpecifyPropertyPages** с использованием библиотеки ATL и предпримите следующие:  
  
1.  Создайте производный класс от [ISpecifyPropertyPagesImpl](../Topic/ISpecifyPropertyPagesImpl%20Class.md).  
  
2.  Добавьте запись для **ISpecifyPropertyPages** к сопоставлению модели COM конкретного типа.  
  
3.  Добавьте запись [PROP\_PAGE](../Topic/PROP_PAGE.md) к сопоставлению свойств для каждой страницы, связанной с элементом управления.  
  
> [!NOTE]
>  При создании стандартный элемент управления с помощью [Мастер элементов управления библиотеки ATL](../atl/reference/atl-control-wizard.md) можно добавлять только записи `PROP_PAGE` к сопоставлению свойств.  Мастер создает необходимый код для других действий.  
  
 Хорошо\- поступаемые контейнеры будут отображаться страницы заданного свойства в том же порядке, в котором записи `PROP_PAGE` в свойстве сопоставить.  В общем случае необходимо поместить стандартные записи страницы свойств выберите записей для пользовательских страниц в сопоставление свойств, так что пользователи получат страницы, относящиеся к элементу управления.  
  
## Пример  
 Следующий класс для элемента управления "Календарь" использует интерфейс **ISpecifyPropertyPages** чтобы определить контейнеры, что его свойства можно установить с помощью пользовательской страницы даты и страница стандартных цветов.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/CPP/specifying-property-pages_1.h)]  
  
## См. также  
 [Страницы свойств](../atl/atl-com-property-pages.md)   
 [Образец ATLPages](../top/visual-cpp-samples.md)