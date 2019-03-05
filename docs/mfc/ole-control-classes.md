---
title: Классы элементов управления OLE
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 86470c3e3e66d6aee2ce532570cea096641d2c1d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304564"
---
# <a name="ole-control-classes"></a>Классы элементов управления OLE

Это основные классы, которые можно использовать при написании элементов управления OLE. `COleControlModule` Класс в модуль управления OLE подобен [CWinApp](../mfc/reference/cwinapp-class.md) класс в приложении. Каждый модуль реализует один или несколько элементов управления OLE; Эти элементы управления, представляются `COleControl` объектов. Эти элементы управления взаимодействовать их с контейнерами с помощью `CConnectionPoint` объектов.

`CPictureHolder` И `CFontHolder` классы инкапсулируют COM-интерфейсы для изображений и шрифтов, хотя `COlePropertyPage` и `CPropExchange` классы позволяют реализовать страницы свойств и сохранения свойств для элемента управления.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
Заменяет `CWinApp` класс для вашего модуля управления OLE. Являются производными от `COleControlModule` класса для разработки модуля управления OLE-объекта. Он предоставляет функции-члены для инициализации модуля управления OLE.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
Являются производными от `COleControl` класса для разработки элемента управления OLE. Является производным от `CWnd`, этот класс наследует все функции объекта окна Windows, а также дополнительные функции OLE, например событием и возможность поддержки методы и свойства.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` Класс определяет специальный тип интерфейса, используемого для взаимодействия с другими объектами OLE и называемый точки подключения. Точки подключения реализует исходящего интерфейса, который может выполнять действия от других объектов, например для срабатывания событий и уведомлений об изменениях.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Инкапсулирует функциональность элемента объекта изображения Windows и `IPicture` COM интерфейс, используемый для реализации настраиваемого свойства изображения элемента управления OLE.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Инкапсулирует функциональность объекта шрифта Windows и `IFont` COM интерфейс, используемый для реализации свойство Font элемента управления OLE.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Отображает свойства OLE управления графическим интерфейсом, аналогичную диалоговое окно.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
Поддерживает реализацию сохранения свойства элементов управления OLE. Аналогично [CDataExchange](../mfc/reference/cdataexchange-class.md) по диалоговым окнам.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
Принимает моникер или строковое представление, его можно преобразовать в моникер и привязывает его синхронно в поток, для которого моникер — это имя.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
Работает аналогично `CMonikerFile`; тем не менее, он выполняет привязку моникера асинхронно в поток, для которого моникер — это имя.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
Позволяет активного документа для получения команд, поступающих в пользовательском интерфейсе контейнера (например, FileNew, открыть, печать и т. д.), а контейнер для получения команд, которые получены в интерфейсе пользователя активного документа.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
Работает с массивами произвольных типов и измерений.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
