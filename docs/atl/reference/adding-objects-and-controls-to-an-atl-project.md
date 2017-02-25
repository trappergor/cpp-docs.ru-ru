---
title: "Добавление объектов и элементов управления в проект ATL. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастер элементов управления ATL"
  - "проекты ATL, добавление элементов управления"
  - "проекты ATL, добавление объектов"
  - "элементы управления [ATL], добавление в проекты"
  - "объекты [C++], добавление в проекты ATL"
  - "мастера [C++], проекты ATL"
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Добавление объектов и элементов управления в проект ATL.
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для добавления объекта или элемента управления в проекте на базе ATL или MFC можно использовать один из мастеров кода ATL.  Для каждого добавляемого объекта СОМ или элемента управления мастер создает CPP\- и H\-файлы, а также RGS\-файл для поддержки реестра на основе скриптов.  В Visual Studio доступны следующие мастера кода ATL.  
  
||||  
|-|-|-|  
|[Простой объект ATL](../../atl/reference/atl-simple-object-wizard.md)|[Диалоговое окно ATL](../../atl/reference/atl-dialog-wizard.md)|[Элемент управления ATL](../../atl/reference/atl-control-wizard.md)|  
|[Страница свойств ATL](../../atl/reference/atl-property-page-wizard.md)|[ASP\-компонент библиотеки ATL](../../atl/reference/atl-active-server-page-component-wizard.md)|[Потребитель ATL OLE DB](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[Добавление поддержки ATL в MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[Мастер компонентов ATL COM\+ 1.0](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[Поставщик ATL OLE DB](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  Перед добавлением объектов ATL в проект следует изучить подробную информацию и требования к объектам в соответствующих разделах справки.  
  
### Добавление объекта или элемента управления с помощью мастера элементов управления ATL.  
  
1.  В обозревателе решений щелкните правой кнопкой мыши узел проекта и в появившемся контекстном меню выберите команду **Добавить**.  Выберите команду **Добавить класс**.  
  
     Открывается диалоговое окно [Добавление класса](../../ide/add-class-dialog-box.md).  
  
2.  Выбрав папку ATL в панели "Категории", выберите объект для вставки на панели "Шаблоны".  Нажмите кнопку **Открыть**.  Откроется мастер кода для выбранного объекта.  
  
    > [!NOTE]
    >  Чтобы добавить объект ATL к проекту MFC, следует добавить поддержку ATL к существующему проекту.  Для этого следуйте инструкциям в разделе [Добавление поддержки ATL в проект MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
     При попытке добавить объект ATL к проекту MFC, не добавив предварительно поддержку ATL, среда Visual Studio попросит указать, следует ли вы добавить поддержку ATL к проекту.  Нажмите **Да**, чтобы добавить поддержку ATL к проекту и открыть выбранный мастер ATL.  
  
## См. также  
 [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md)   
 [Типы проектов Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Программирование с использованием ATL и кода среды выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Конфигурации по умолчанию проекта ATL](../../atl/reference/default-atl-project-configurations.md)