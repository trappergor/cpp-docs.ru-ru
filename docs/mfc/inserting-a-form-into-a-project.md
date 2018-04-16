---
title: Вставка формы в проект | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 968c24a4f64b88be6de95f0f1dd98c09eb494a97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="inserting-a-form-into-a-project"></a>Вставка формы в проект
Forms предоставляют удобный контейнер для элементов управления. Можно легко вставить формы на основе MFC в приложении, при условии, что приложение поддерживает библиотеки MFC.  
  
### <a name="to-insert-a-form-into-your-project"></a>Вставка формы в проект  
  
1.  Выберите проект, к которому требуется добавить форму из представления классов и щелкните правой кнопкой мыши.  
  
2.  В контекстном меню щелкните **добавить** и нажмите кнопку **Добавление класса**.  
  
     Если **новую форму** команда недоступна, проект может быть основана на Active Template Library (ATL). Чтобы добавить форму в проект ATL, вам следует [настроить определенные параметры](../atl/reference/application-settings-atl-project-wizard.md) при первом создании проекта.  
  
3.  Из **MFC** папку, нажмите кнопку **класса MFC**.  
  
4.  С помощью мастера классов MFC сделайте новый класс является производным от [CFormView](../mfc/reference/cformview-class.md).  
  
 Visual C++ добавляет формы на приложение, открыв его в редакторе диалоговых окон, чтобы можно было начать добавление элементов управления, а работу его макет.  
  
 Может потребоваться выполнить следующие дополнительные действия (не применимо для приложений на базе диалогового окна):  
  
1.  Переопределить `OnUpdate` функции-члена.  
  
2.  Реализуйте функцию-член для перемещения данных из представления в документе.  
  
3.  Создание `OnPrint` функции-члена.  
  
## <a name="see-also"></a>См. также  
 [Представления форм](../mfc/form-views-mfc.md)

