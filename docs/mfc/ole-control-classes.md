---
title: "Классы элементов управления OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX - классы [C++]"
  - "ActiveX - классы элементов управления [C++]"
  - "элементы управления ActiveX [C++], классы элементов управления OLE"
  - "пользовательские элементы управления [MFC], классы"
  - "OLE - классы элементов управления [C++]"
  - "элементы управления OLE [C++], классы"
  - "классы компонентов многократного использования"
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Классы элементов управления OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти основные классы, используемые при создании элементов управления OLE.  Класс `COleControlModule` в модуле элемента управления OLE как класс [CWinApp](../mfc/reference/cwinapp-class.md) в приложении.  Каждый модуль реализует один или несколько элементов управления OLE; эти элементы управления представлены объектами `COleControl`.  Эти элементы управления взаимодействуют с их контейнерами с помощью объектов `CConnectionPoint`.  
  
 Классы `CPictureHolder` и `CFontHolder` инкапсулируют интерфейсов модели COM примеры и шрифтов, а классы `COlePropertyPage` и `CPropExchange` помогают реализовать страницы свойств и сохранение свойства для элемента управления.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Заменяет класс `CWinApp` для данного модуля элемента управления OLE.  Наследование от класса `COleControlModule` разрабатывать модульный объект элемента управления OLE.  Он предоставляет функции\-члены для инициализации модуля элемента управления OLE.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Наследование от класса `COleControl` для создания пользовательского элемента управления OLE.  Производное от `CWnd`, этот класс наследует все функциональные возможности объекта окна Windows и дополнительно функция OLE\- функции, такие как включение событий и возможность поддерживать методы и свойства.  
  
 [CConnectionPoint](../Topic/CConnectionPoint%20Class.md)  
 Класс `CConnectionPoint` определяет вызывается особый тип интерфейса, используемый для связи с другими объектами OLE, точкой подключения.  Точка подключения реализует исходящий интерфейс, который может инициировать действия на другие объекты, такие как события и включения уведомлений об изменении.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Инкапсулирует функции объекта рисунка Windows и COM\-интерфейса `IPicture`; используется для реализации пользовательского свойства рисунков элемента управления OLE.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Инкапсулирует функции объекта шрифта Windows и COM\-интерфейса `IFont`; используется для реализации свойства font элемента управления OLE.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Отображает свойства элемента управления OLE в графическом интерфейсе, аналогично диалоговому окну.  
  
 [CPropExchange](../Topic/CPropExchange%20Class.md)  
 Поддерживает реализацию сохранения свойств для элементов управления OLE.  Аналогичный в [CDataExchange](../Topic/CDataExchange%20Class.md) для диалоговых окон.  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
 Принимает моникер или строковое представление, он может выполнять в моникер и привязывает его одновременно в поток, для которого моникер имя.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Работает аналогично `CMonikerFile`; однако он привязывает моникер асинхронно в поток, для которого моникер имя.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Позволяет активный документ для получения команды, расположенных в интерфейсе пользователя контейнера \(например, FileNew, открытый, печать и т д\) и позволяет контейнер для получения команды, расположенных в интерфейсе пользователя активного документа.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Для работы с массивами произвольных типов и измерения.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)