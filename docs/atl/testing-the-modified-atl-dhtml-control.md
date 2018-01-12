---
title: "Тестирование измененный элемент управления ATL DHTML | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5ecb8526ec82e0f2d18c5306a94dd7f0160803b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Тестирование измененный элемент управления ATL DHTML
Пробное использование нового элемента управления для просмотра их работу.  
  
#### <a name="to-build-and-test-the-modified-control"></a>Построение и тестирование измененного элемента управления  
  
1.  Перестройте проект и откройте его в тестовом контейнере. В разделе [тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md) сведения о том, как получить доступ к контейнеру теста.  
  
     Размер элемента управления для отображения всех кнопок, которые вы добавили.  
  
2.  Изучите две кнопки, которые вставлены путем изменения HTML. Каждая кнопка имеет метку, определенных в [изменения элемента управления ATL DHTML](../atl/modifying-the-atl-dhtml-control.md): **обновление** и **HelloHTML**.  
  
3.  Проверьте две новые кнопки, чтобы увидеть, как они работают.  
  
 Теперь можно проверьте методы, которые не являются частью пользовательского интерфейса.  
  
1.  Выделите элемент управления, чтобы активировать границы.  
  
2.  На **управления** меню, нажмите кнопку **вызов методов**.  
  
 Методы в списке с меткой **имя метода** представляют собой методы, которые могут вызывать контейнера: `MethodInvoked` и `GoToURL`. Все другие методы управляются пользовательского интерфейса.  
  
1.  Выберите способ вызова неуправляемого кода и нажмите кнопку `Invoke` для отображения окна сообщения метода или для перехода к www.microsoft.com.  
  
2.  В **вызов методов** диалоговое окно, нажмите кнопку **закрыть**.  
  
 Дополнительные сведения о различных элементов и файлов, составляющих элемент управления ATL DHTML см. в разделе [определения элементов управления DHTML проекта](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## <a name="see-also"></a>См. также  
 [Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

