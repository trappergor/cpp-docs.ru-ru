---
title: "Создание интерфейса COM (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.com.creating.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "интерфейсы COM, создание"
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание интерфейса COM (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В Visual C\+\+ имеются мастера и шаблоны для создания проектов, использующих определяющие и диспетчерские интерфейсы COM для объектов COM и классов автоматизации.  
  
 Эти мастера можно использовать для выполнения следующих трех типовых задач.  
  
-   [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Добавить поддержку ATL в приложение MFC после создания проекта MFC можно, используя [мастер приложений MFC](../Topic/MFC%20Application%20Wizard.md) с последующим запуском мастера кода **Добавить в MFC поддержку ATL**.  Эта поддержка действует только для простых объектов COM, добавленных в проект исполняемого приложения MFC или библиотеки DLL.  Эти объекты ATL могут иметь множество интерфейсов.  
  
-   [Создание элемента управления ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Откройте [Мастер элементов ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md), чтобы создать элемент управления ActiveX с диспетчерским интерфейсом и картой событий, определенных в IDL\-файле и управляющем классе соответственно.  
  
-   [Добавление элемента управления ATL](../atl/reference/adding-an-atl-control.md)  
  
     Используйте [Мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md) в сочетании с [Мастером элементов управления ATL](../atl/reference/atl-control-wizard.md) для создания элемента управления ActiveX ATL.  
  
     Можно также добавить элемент управления ATL в проект MFC, в который был добавлена поддержка ATL, как описано выше.  Кроме того, если выбрать **Элемент управления ATL** в диалоговом окне **Добавление класса** в условиях, когда поддержка ATL еще не добавлена в проект MFC, в Visual Studio отображается диалоговое окно с предложением подтвердить добавление поддержки ATL в проект MFC.  
  
     Этот мастер создает исходный код IDL и карту COM в классах проекта.  
  
 В открытом проекте ATL диалоговое окно [Добавление класса](../ide/add-class-dialog-box.md) позволяет выбирать дополнительные мастера и шаблоны для добавления интерфейсов COM в проект.  Следующие мастера позволяют также установить один или несколько интерфейсов для объекта:  
  
-   [Мастер компонентов ATL COM\+ 1.0](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [Мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md)  
  
-   [Мастер ASP\-компонентов библиотеки ATL](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md)  
  
 Кроме того, вы можете реализовать новые интерфейсы для своего элемента управления COM, щелкнув правой кнопкой мыши управляющий класс объекта в окне классов и выбрав команду [Реализовать интерфейс](../Topic/Implement%20Interface%20Wizard.md).  
  
> [!NOTE]
>  В Visual Studio нет мастера для добавления интерфейса в проект.  Добавить интерфейс в проект ATL или [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) можно путем добавления простого объекта с помощью [мастера простых объектов ATL](../atl/reference/atl-simple-object-wizard.md).  Вместо этого вы можете открыть IDL\-файл проекта и создать интерфейс, введя следующий код:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Дополнительные сведения см. в разделе [Реализация интерфейса](../ide/implementing-an-interface-visual-cpp.md) и [Добавление объектов и элементов управления в проект ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
 Visual C\+\+ предоставляет несколько способов просмотра и [редактирования интерфейсов COM](../ide/editing-a-com-interface.md), определенных для проектов.  В [окне классов](http://msdn.microsoft.com/ru-ru/8d7430a9-3e33-454c-a9e1-a85e3d2db925) отображаются значки всех интерфейсов \(в том числе диспетчерских\), определенных в IDL\-файле проекта C\+\+.  
  
 Для классов объектов COM на базе ATL в окне классов по информации из карты COM класса ATL отображаются связи между классом ATL и всеми интерфейсами, которые он реализует.  
  
 В окне классов и его контекстных меню вы можете работать с интерфейсами следующим образом:  
  
-   Добавлять объекты ATL в приложение на базе MFC.  
  
-   Добавлять методы, свойства и события.  
  
-   Непосредственно переходить к коду интерфейса элемента, дважды щелкнув данный элемент.  
  
## См. также  
 [Создание проектов для рабочего стола с помощью мастеров приложений](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)