---
title: "Testing the Modified ATL DHTML Control | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML controls, проверка"
  - "элементы управления HTML, проверка"
  - "testing controls"
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Testing the Modified ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Попробуйте вне новый элемент управления, чтобы проверить, как он работает.  
  
#### Построение и тестирование измененный элемент управления  
  
1.  Перестройте проект и откройте его в тестовом контейнере.  См. раздел [свойства и события тестирования с тестовым контейнером](../mfc/testing-properties-and-events-with-test-container.md) дополнительные сведения о доступе к тестовый контейнер.  
  
     Измените размер элемента управления, чтобы отобразить все кнопки добавления.  
  
2.  Просмотрите 2 кнопки, вставленным путем редактирования HTML.  Каждая кнопка содержит метку, указанной в [Изменение элемент управления DHTML библиотеки ATL](../atl/modifying-the-atl-dhtml-control.md): **Обновить** и **HelloHTML**.  
  
3.  Проверьте 2 новых кнопки, чтобы просмотреть, как они работают.  
  
 Теперь тест методы, которые не являются частью пользовательского интерфейса.  
  
1.  Выберите элемент управления, поэтому граница активируется.  
  
2.  В меню **Управление** нажмите кнопку **Invoke Methods**.  
  
 Методы в списке **Имя метода** методы, которые может вызвать контейнер. `MethodInvoked`  и  `GoToURL`.  Все другие методы управляются пользовательским интерфейсом.  
  
1.  Выберите метод, который необходимо вызвать, и щелкните `Invoke` для отображения окна сообщения метода или для перехода на www.microsoft.com.  
  
2.  В диалоговом окне **Invoke Methods** нажмите кнопку **Закрыть**.  
  
 Дополнительные сведения о различных элементах и файлов, составляющих элемент управления DHTML библиотеки ATL см. в разделе [Идентификация элементов проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## См. также  
 [Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)