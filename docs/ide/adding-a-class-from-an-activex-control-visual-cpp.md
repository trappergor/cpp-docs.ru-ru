---
title: "Добавление класса из элемента управления ActiveX (Visual C++) | Microsoft Docs"
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
  - "элементы управления ActiveX [C++], классы - добавление"
  - "классы [C++], создание"
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Добавление класса из элемента управления ActiveX (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью этого мастера можно создать класс MFC из интерфейса в доступном элементе управления ActiveX.  Класс MFC можно добавить в [приложение MFC](../mfc/reference/creating-an-mfc-application.md), [DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md) или [элемент управления ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Чтобы добавить класс из элемента управления ActiveX, не нужно создавать проект MFC с включенной функцией автоматизации.  
  
 Элемент управления ActiveX ― это многократно используемый компонент программы, основанный на модели COM, который поддерживает широкий диапазон функциональных возможностей OLE и может быть настроен для соответствия многим потребностям программного обеспечения.  Элементы управления ActiveX разработаны для использования как в обычных контейнерах элементов управления ActiveX, так и в интернет\-страницах.  
  
### Добавление класса MFC из элемента управления ActiveX  
  
1.  В **обозревателе решений** или в [представлении классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой мыши имя проекта, в который требуется добавить класс элементов управления ActiveX.  
  
2.  Выберите в контекстном меню команду **Добавить**, а затем **Добавить класс**.  
  
3.  В области "Шаблоны" диалогового окна [Добавление класса](../ide/add-class-dialog-box.md) щелкните **класс MFC элемента управления ActiveX**, а затем нажмите кнопку **Открыть**, чтобы открыть [Мастер добавления классов из элемента управления ActiveX](../ide/add-class-from-activex-control-wizard.md).  
  
 С помощью мастера можно добавить несколько интерфейсов в элемент управления ActiveX.  Можно также создавать классы из нескольких элементов управления ActiveX за один сеанс мастера.  
  
 Можно добавлять классы как из элементов управления ActiveX, зарегистрированных в системе, так и из элементов управления ActiveX, содержащихся в файлах библиотек типов \(TLB, OLB, DDL, OCX или EXE\), не регистрируя их в системе.  Дополнительные сведения о регистрации элементов управления ActiveX см. в разделе [Регистрация элементов управления библиотеки OLE](../Topic/Registering%20OLE%20Controls.md).  
  
 Мастер создает класс MFC, производный от классов [CWnd](../Topic/CWnd%20Class.md) или [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавляемого из выбранного элемента управления ActiveX.  
  
## См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)