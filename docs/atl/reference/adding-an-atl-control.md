---
title: "Добавление элемента управления ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3200ea0fc8241007c1c97c1ab296166eb7889734
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-control"></a>Добавление элемента управления ATL
Этот мастер используется для добавления объекта пользовательского интерфейса в проект, который поддерживает интерфейсы всех потенциальных контейнеров. Для поддержки этих интерфейсов проект должен быть создан как приложение ATL или как приложение MFC с поддержкой ATL. Можно использовать [мастер проектов ATL](../../atl/reference/atl-project-wizard.md) для создания приложения ATL или [добавить объект ATL в приложение MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) для реализации поддержки ATL в приложении MFC.  
  
### <a name="to-add-an-atl-control-to-your-project"></a>Для добавления в проект элемента управления ATL  
  
1.  В любом **обозревателе решений** или [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому требуется добавить простой объект ATL.  
  
2.  Нажмите кнопку **добавить** из контекстного меню и нажмите кнопку **Добавление класса**.  
  
3.  В [добавить класс](../../ide/add-class-dialog-box.md) щелкните в области шаблонов диалогового **управления ATL**, а затем нажмите кнопку **добавить** для отображения [мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md).  
  
 С помощью **мастер элементов управления ATL**, можно создать один из трех типов элементов управления:  
  
-   Стандартный элемент управления  
  
-   Составной элемент управления  
  
-   Элемент управления DHTML  
  
 Кроме того, можно уменьшить размер элемента управления и удалить интерфейсы, не используемые большинством контейнеров, выбрав **минимальный элемент управления** на **параметры** странице мастера.  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей в составной элемент управления](../../atl/adding-functionality-to-the-composite-control.md)   
 [Основные принципы работы COM-объекты ATL](../../atl/fundamentals-of-atl-com-objects.md)   
 [Пример ATLFire](http://msdn.microsoft.com/en-us/5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)

