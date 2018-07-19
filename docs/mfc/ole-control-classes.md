---
title: Классы элементов управления OLE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5dcbda85c33bab37babe5da861067d25cf31e32c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355364"
---
# <a name="ole-control-classes"></a>Классы элементов управления OLE
Это основной классы, используемые при записи элементов управления OLE. `COleControlModule` Класс в модуль управления OLE аналогичен [CWinApp](../mfc/reference/cwinapp-class.md) класс в приложении. Каждый модуль реализует один или несколько элементов управления OLE; Эти элементы управления, представляются `COleControl` объектов. Эти элементы управления взаимодействуют с помощью контейнеров `CConnectionPoint` объектов.  
  
 `CPictureHolder` И `CFontHolder` классы инкапсулируют COM-интерфейсы для изображений и шрифтов, а `COlePropertyPage` и `CPropExchange` классы позволяют реализовать страниц свойств и сохранения свойств для элемента управления.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Заменяет `CWinApp` класса для модуля управления OLE. Является производным от `COleControlModule` класса для разработки модуля управления OLE-объекта. Он предоставляет функции-члены для инициализации модуля управления OLE.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Является производным от `COleControl` класса для разработки элемента управления OLE. Производное от `CWnd`, этот класс наследует все функциональные возможности объекта окна Windows, а также дополнительные функциональные возможности определенного OLE, например событием и возможность поддержки методы и свойства.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 `CConnectionPoint` Класс определяет особый тип интерфейса, используемый для взаимодействия с другими объектами OLE и называемый точкой подключения. Точки подключения реализует исходящий интерфейс, который способен инициации действий на другие объекты, например, срабатывание события и уведомления об изменениях.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Инкапсулирует функциональность объекта изображения Windows и `IPicture` COM интерфейса; используется для реализации настраиваемого свойства изображения элемента управления OLE.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Инкапсулирует функциональность объекта шрифта Windows и `IFont` COM интерфейса; используется для реализации свойство Font элемента управления OLE.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 В графическом интерфейсе Подобно диалоговому контролировать отображение свойств OLE.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 Поддерживает реализацию сохранения свойств элементов управления OLE. Аналогично [CDataExchange](../mfc/reference/cdataexchange-class.md) для диалоговых окон.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Принимает строковое представление, его можно преобразовать в моникер или моникера и привязывает его синхронно в поток, для которого моникер — это имя.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Работает так же, как `CMonikerFile`, однако он привязывает моникер асинхронно в поток, для которого моникер — это имя.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Позволяет активного документа для получения команд, которые происходят в пользовательском интерфейсе контейнера (например, FileNew, Open, печати и т. д), а контейнер для получения команд, поступающих в пользовательском интерфейсе активного документа.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Работает с массивами произвольных типов и измерений.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

