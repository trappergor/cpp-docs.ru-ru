---
title: Классы элементов управления OLE
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 47c28520d592c4bd49ab6cb40edbb2f5ddf59846
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447650"
---
# <a name="ole-control-classes"></a>Классы элементов управления OLE

Это основные классы, используемые при написании элементов управления OLE. Класс `COleControlModule` в модуле управления OLE аналогичен классу [CWinApp](../mfc/reference/cwinapp-class.md) в приложении. Каждый модуль реализует один или несколько элементов управления OLE. Эти элементы управления представлены `COleControl` объектами. Эти элементы управления взаимодействуют с их контейнерами с помощью `CConnectionPoint` объектов.

Классы `CPictureHolder` и `CFontHolder` инкапсулируют интерфейсы COM для изображений и шрифтов, а классы `COlePropertyPage` и `CPropExchange` помогают реализовать страницы свойств и сохраняемость свойств для элемента управления.

[колеконтролмодуле](../mfc/reference/colecontrolmodule-class.md)<br/>
Заменяет класс `CWinApp` для модуля управления OLE. Производные от класса `COleControlModule` для разработки объекта модуля управления OLE. Он предоставляет функции элементов для инициализации модуля элемента управления OLE.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
Производные от класса `COleControl` для разработки элемента управления OLE. Производный от `CWnd`этот класс наследует все функциональные возможности объекта окна Windows, а также дополнительные функции, относящиеся к OLE, такие как срабатывание событий и возможность поддержки методов и свойств.

[кконнектионпоинт](../mfc/reference/cconnectionpoint-class.md)<br/>
Класс `CConnectionPoint` определяет особый тип интерфейса, используемого для взаимодействия с другими OLE-объектами, называемыми точкой соединения. Точка соединения реализует исходящий интерфейс, который может инициировать действия с другими объектами, такими как события обработки и уведомления об изменении.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Инкапсулирует функциональные возможности объекта изображения Windows и `IPicture`ного COM-интерфейса; используется для реализации пользовательского свойства изображения элемента управления OLE.

[кфонсолдер](../mfc/reference/cfontholder-class.md)<br/>
Инкапсулирует функциональные возможности объекта шрифта Windows и `IFont`ного COM-интерфейса; используется для реализации свойства «стандартный шрифт» элемента управления OLE.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Отображает свойства элемента управления OLE в графическом интерфейсе аналогично диалоговому окну.

[кпропексчанже](../mfc/reference/cpropexchange-class.md)<br/>
Поддерживает реализацию сохраняемости свойств для элементов управления OLE. Аналог с [кдатаексчанже](../mfc/reference/cdataexchange-class.md) для диалоговых окон.

[кмоникерфиле](../mfc/reference/cmonikerfile-class.md)<br/>
Принимает моникер или строковое представление, которое можно преобразовать в моникер, и выполняет синхронную привязку к потоку, для которого имя моникера является именем.

[касинкмоникерфиле](../mfc/reference/casyncmonikerfile-class.md)<br/>
Работает аналогично `CMonikerFile`; Однако он привязывает моникер асинхронно к потоку, для которого имя моникера является именем.

[кдатапаспроперти](../mfc/reference/cdatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

[ккачеддатапаспроперти](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.

[колекмдуи](../mfc/reference/colecmdui-class.md)<br/>
Позволяет активному документу принимать команды, происходящие в пользовательском интерфейсе контейнера (например, Филенев, Open, Print и т. д.), и позволяет контейнеру принимать команды, происходящие в пользовательском интерфейсе активного документа.

[колесафеаррай](../mfc/reference/colesafearray-class.md)<br/>
Работает с массивами произвольного типа и измерения.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
