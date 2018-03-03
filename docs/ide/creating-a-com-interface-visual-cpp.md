---
title: "Создание интерфейса COM (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.com.creating.interfaces
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7b5820686c3e6f01c37cbf527d0e631e5bcc25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-com-interface-visual-c"></a>Создание интерфейса COM (Visual C++)
Visual C++ предоставляет мастеры и шаблоны для создания проектов, использующих определение интерфейсов COM и диспетчерских для COM-объектов и классы автоматизации.  
  
 Эти мастера можно использовать для выполнения следующих трех задач:  
  
-   [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Добавление поддержки ATL в приложение MFC после создания проекта MFC с помощью [мастер приложений MFC](../mfc/reference/mfc-application-wizard.md) , а затем выполнить **добавить поддержку ATL в MFC** мастер создания кода. Эта поддержка действует только для простых объектов COM, добавленных в проект библиотеки DLL или исполняемого файла MFC. Эти объекты ATL могут иметь несколько интерфейсов.  
  
-   [Создание элемента ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Откройте [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md) для создания элемента управления ActiveX с disp-интерфейса и картой событий, определенных в IDL-файл и класс элемента управления, соответственно.  
  
-   [Добавление элемента управления ATL](../atl/reference/adding-an-atl-control.md)  
  
     Использование сочетания [мастер проектов ATL](../atl/reference/atl-project-wizard.md) и [мастер элементов управления ATL](../atl/reference/atl-control-wizard.md) для создания элемента управления ActiveX библиотеки ATL.  
  
     Можно также добавить элемент управления ATL в проект MFC, в которую была добавлена поддержка ATL, как описано выше. Кроме того при выборе **управления ATL** в **добавить класс** диалоговое окно и иметь еще не добавлена поддержка ATL в проект MFC, Visual Studio отображает диалоговое окно с предложением подтвердить добавление поддержки ATL в вашей Проект MFC.  
  
     Этот мастер создает исходный код IDL и карту COM в классах проекта.  
  
 После создания проекта ATL открыть, [добавить класс](../ide/add-class-dialog-box.md) диалоговое окно позволяет выбрать дополнительные мастера и шаблоны для добавления интерфейсов COM в проект. Следующие мастера позволяют также установить один или несколько интерфейсов для объекта:  
  
-   [Мастер компонентов ATL COM+ 1.0](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [Мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md)  
  
-   [Мастер ASP-компонента ATL](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md)  
  
 Кроме того, можно реализовать новые интерфейсы для своего элемента управления COM, щелкнув правой кнопкой мыши класс объекта элемента управления в представлении классов команду [реализовать интерфейс](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio не предоставляет мастер, чтобы добавить интерфейс в проект. Можно добавить интерфейс в проект ATL или [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) путем добавления простого объекта с помощью [мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md). Можно также открыть IDL-файл проекта и создать интерфейс, введя:  
  
```  
interface IMyInterface {  
};  
  
```  
  
 В разделе [реализации интерфейса](../ide/implementing-an-interface-visual-cpp.md) и [Добавление объекты и элементы управления в проект ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) для получения дополнительной информации.  
  
 Visual C++ предоставляет несколько способов просмотра и [редактирования интерфейсов COM,](../ide/editing-a-com-interface.md) определенных для проектов. [Представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) отображаются значки для любого интерфейса или disp-интерфейса, определенных в IDL-файле проекта C++.  
  
 Для классов объектов COM на базе ATL представление классов считывает карты COM класса ATL отображаются связи между классом ATL и всеми интерфейсами, которые он реализует.  
  
 В представлении классов и его контекстных меню можно работать с интерфейсами следующим образом:  
  
-   Добавляете объекты ATL в приложение на основе MFC.  
  
-   Добавьте методы, свойства и события.  
  
-   Выполняется переход непосредственно к коду интерфейса элемента, дважды щелкнув элемент.  
  
## <a name="see-also"></a>См. также  
 [Создание проектов для рабочего стола с помощью мастеров приложений](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)