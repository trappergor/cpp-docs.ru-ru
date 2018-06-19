---
title: Тестирование измененный элемент управления ATL DHTML | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b140788cd409aa5a11f93689e96fa40c1a167dfe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360349"
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

