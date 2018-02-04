---
title: "Добавление класса (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac87368f2bd38c32425799103fa3999dd11b3298
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2018
---
# <a name="adding-a-class-visual-c"></a>Добавление класса (Visual C++)
Чтобы добавить класс в проект Visual C++ в **обозревателе решений**, щелкните правой кнопкой мыши проект, нажмите кнопку **добавить**и нажмите кнопку **класса**. При этом откроется [класс диалоговое окно Добавление](../ide/add-class-dialog-box.md) диалоговое окно.  
  
 При добавлении класса необходимо указать имя, которое отличается от классов, которые уже существуют в MFC или ATL. Если указать имя, которое уже существует в одной из библиотек, интегрированная среда разработки показывает сообщение об ошибке.  
  
 Если соглашение об именовании проекта необходимо использовать имя существующей, затем можно просто изменить регистр одну или несколько букв в имени, так как C++ учитывается регистр. Например нельзя назвать класс `CDocument`, можно назвать его `cdocument`.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>Класс какого типа вы хотите добавить?  
 В **добавить класс** диалогового окна, при разворачивании **Visual C++** узел в левой области отображаются несколько групп установленных шаблонов. Включать группы **CLR**, **ATL**, **MFC**, и **C++**. При выборе группы на средней панели отображается список доступных шаблонов в этой группе. Каждый шаблон содержит файлы и исходный код, которые требуются для класса.  
  
 Чтобы создать новый класс, в средней области выберите шаблон, введите имя класса в **имя** и нажмите кнопку **добавить**. При этом откроется **мастер добавления класса** , можно указать параметры для этого класса.  
  
-   Дополнительные сведения о создании классов MFC см. в разделе [класса MFC](../mfc/reference/adding-an-mfc-class.md).  
  
-   Дополнительные сведения о создании классов ATL см. в разделе [простых объектов ATL](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Шаблон **Добавление поддержки ATL в MFC** не создавайте класс, а настраивает проект на использование библиотеки ATL. Дополнительные сведения см. в разделе [поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Чтобы создать класс C++, который не использует MFC, ATL или CLR, используйте **класс C++** шаблона в **C++** группе установленных шаблонов. Дополнительные сведения см. в разделе [Добавление универсального класса C++](../ide/adding-a-generic-cpp-class.md).  
  
 Доступны два типа форм классов C++. Первая из них, [класс CFormView](../mfc/reference/cformview-class.md) создает класс MFC. Второй создает класс Windows Forms со средой CLR.  
  
## <a name="see-also"></a>См. также  
 [Создание приложений MFC на основе форм](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Добавить класс-диалоговое окно](../ide/add-class-dialog-box.md)   
 [Создание проектов для рабочего стола с помощью мастеров приложений](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)