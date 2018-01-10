---
title: "Реализация интерфейса (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 896ada2c46c68a794265e7344e9b7f7c7f91aebe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-an-interface-visual-c"></a>Реализация интерфейса (Visual C++)
Для реализации интерфейса, необходимо создан проект как COM-приложение ATL или как приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../atl/reference/atl-project-wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
 После создания проекта, чтобы реализовать интерфейс, необходимо сначала добавить объект ATL. В разделе [Добавление объекты и элементы управления в проект ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) список мастеров для добавления объектов в проекты ATL.  
  
> [!NOTE]
>  Мастер не поддерживает диалоговые окна ATL, веб-служб XML с использованием ATL, объекты производительности и счетчики производительности.  
  
 Если вы [добавить элемент управления ATL](../atl/reference/adding-an-atl-control.md), можно указать, следует ли реализовать интерфейсы по умолчанию, перечисленных на [интерфейсы](../atl/reference/interfaces-atl-control-wizard.md) страницу, мастера и определенных в файле atlcom.h.  
  
 После добавления объекта или элемента управления, можно реализовать другие интерфейсы, расположенные в любой доступной библиотеке типов, с помощью мастера реализации интерфейса.  
  
 При добавлении нового интерфейса необходимо добавить его вручную в IDL-файл проекта. В разделе [Добавление нового интерфейса в проект ATL](../atl/reference/adding-a-new-interface-in-an-atl-project.md) для получения дополнительной информации.  
  
### <a name="to-implement-an-interface"></a>Для реализации интерфейса  
  
1.  В представлении классов щелкните правой кнопкой мыши имя класса объекта ATL.  
  
2.  Нажмите кнопку **добавить** из контекстного меню и нажмите кнопку **реализовать интерфейс** для отображения [мастер реализации интерфейсов](../ide/implement-interface-wizard.md).  
  
3.  Выберите интерфейсы для реализации из соответствующих библиотек типов и нажмите кнопку **Готово**.  
  
4.  В представлении класса разверните объекта базовых классов и интерфейсов узел, чтобы увидеть интерфейс реализован, а затем разверните узел этого интерфейса, чтобы увидеть его доступные свойства, методы и события.  
  
    > [!NOTE]
    >  Можно также использовать [обозревателя объектов](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) для изучения элементов интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Редактирование интерфейса COM](../ide/editing-a-com-interface.md)