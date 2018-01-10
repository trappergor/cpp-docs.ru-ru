---
title: "Тестирование свойств и событий с использованием тестового контейнера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 381f4e421b63b2ba48fe649a30e5bf7648b50d27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="testing-properties-and-events-with-test-container"></a>Тестирование свойств и событий с использованием тестового контейнера
Тестовый контейнер приложения, поставляется в Visual C++ является контейнер элемента управления ActiveX для тестирования и отладки элементов управления ActiveX. Тестовый контейнер позволяет разработчику элемента управления для проверки функциональности элемента управления, изменив его свойства, вызывая его методы и создавая его события. Тестовый контейнер можно отобразить журналы уведомлений привязки данных, а также предоставляет средства для тестирования функциональности элемента управления ActiveX сохраняемости: можно сохранить свойства в поток или вложенного хранилища, загрузите их и изучить сохраненного потока данных. В этом разделе описывается использование основных возможностей тестового контейнера элемента. Для получения дополнительных сведений выберите **справки** меню во время выполнения тестового контейнера.  
  
### <a name="to-access-the-activex-control-test-container"></a>Для доступа к контейнеру теста элемент управления ActiveX  
  
1.  Построение [образца TSTCON: контейнер для проверки элементов ActiveX](../visual-cpp-samples.md).  
  
### <a name="to-test-your-activex-control"></a>Чтобы протестировать элемент управления ActiveX  
  
1.  На **изменить** меню тестового контейнера элемента щелкните **вставить новый элемент управления**.  
  
2.  В **вставить элемент** выберите нужный элемент управления и нажмите кнопку **ОК**. Элемент управления будет отображаться в контейнере элемента управления.  
  
    > [!NOTE]
    >  Если элемент управления не указан в **вставить элемент** диалогового окна поле, убедитесь, что вы зарегистрировали его с **Регистрация элементов управления** из **файл** меню теста Контейнер.  
  
 На этом этапе можно проверить свойства или события элемента управления.  
  
#### <a name="to-test-properties"></a>Чтобы проверить свойства  
  
1.  На **управления** меню, нажмите кнопку **вызов методов**.  
  
2.  В **имя метода** раскрывающегося списка выберите метод PropPut для свойства, необходимо проверить.  
  
3.  Изменить **значение параметра** или **тип параметра** и выберите команду **задание значения** кнопки.  
  
4.  Нажмите кнопку **Invoke** нужно применить новое значение объекту.  
  
     Свойство теперь содержит новое значение.  
  
#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Чтобы протестировать события и указать конечное расположение данных о событиях.  
  
1.  На **параметры** меню, нажмите кнопку **ведение журнала**.  
  
2.  Укажите назначение данных о событиях.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Практическое руководство. Отладка элемента управления ActiveX](/visualstudio/debugger/how-to-debug-an-activex-control)
