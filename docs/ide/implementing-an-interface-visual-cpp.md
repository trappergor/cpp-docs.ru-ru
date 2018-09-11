---
title: Реализация интерфейса (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfee61f1632fad2d762c41149c1bc302a1c4b9da
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691990"
---
# <a name="implementing-an-interface-visual-c"></a>Реализация интерфейса (Visual C++)
Для реализации интерфейса нужно создать проект как COM-приложение ATL или как приложение MFC с поддержкой ATL. Вы можете использовать [Мастер проектов ATL](../atl/reference/atl-project-wizard.md), чтобы создать приложение ATL, или [добавить объект ATL в свое приложение MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md), чтобы реализовать поддержку ATL для приложения MFC.  
  
 Создав проект для реализации интерфейса, нужно сначала добавить объект ATL. См. раздел [Добавление объектов и элементов управления в проект ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md), где перечислены мастеры, добавляющие объекты в проект ATL.  
  
> [!NOTE]
>  Мастер не поддерживает диалоговые окна ATL, XML-веб-службы с использованием ATL, объекты производительности и счетчики производительности.  
  
 Если вы [добавляете элемент управления ATL](../atl/reference/adding-an-atl-control.md), можно указать, требуется ли реализовать интерфейсы по умолчанию, перечисленные на странице [Интерфейсы](../atl/reference/interfaces-atl-control-wizard.md) этого мастера и определенные в файле atlcom.h.  
  
 После добавления объекта или элемента управления можно реализовать другие интерфейсы, расположенные в любой доступной библиотеке типов, с помощью мастера реализации интерфейса.  
  
 При добавлении нового интерфейса нужно добавить его вручную в IDL-файл проекта. Дополнительные сведения см. в разделе [Добавление нового интерфейса в проект ATL](../atl/reference/adding-a-new-interface-in-an-atl-project.md).  
  
### <a name="to-implement-an-interface"></a>Реализация интерфейса  
  
1.  В представлении классов щелкните правой кнопкой мыши имя класса для объекта ATL.  
  
2.  Выберите пункт **Добавить** в контекстном меню и щелкните **Реализовать интерфейс**, чтобы отобразить [Мастер реализации интерфейса](../ide/implement-interface-wizard.md).  
  
3.  Выберите реализуемые интерфейсы в соответствующих библиотеках типов и нажмите кнопку **Готово**.  
  
4.  В представлении класса разверните узел "Базы и интерфейсы" объекта, чтобы увидеть реализованный интерфейс, а затем разверните узел этого интерфейса, чтобы просмотреть его доступные свойства, методы и события.  
  
    > [!NOTE]
    >  Вы также можете использовать [Обозреватель объектов](/visualstudio/ide/viewing-the-structure-of-code) для просмотра членов интерфейса.  
  
## <a name="see-also"></a>См. также  
 [Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Редактирование интерфейса COM](../ide/editing-a-com-interface.md)