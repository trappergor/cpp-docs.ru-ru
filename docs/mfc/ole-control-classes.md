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
ms.openlocfilehash: 5aa3899dca5a42cf789dc6dfd4701547495ec618
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617764"
---
# <a name="ole-control-classes"></a>Классы элементов управления OLE

Это основные классы, используемые при написании элементов управления OLE. `COleControlModule`Класс в модуле управления OLE аналогичен классу [CWinApp](reference/cwinapp-class.md) в приложении. Каждый модуль реализует один или несколько элементов управления OLE. Эти элементы управления представлены `COleControl` объектами. Эти элементы управления взаимодействуют с их контейнерами с помощью `CConnectionPoint` объектов.

`CPictureHolder`Классы и `CFontHolder` ИНКАПСУЛИРУЮТ интерфейсы COM для изображений и шрифтов, а `COlePropertyPage` `CPropExchange` классы и помогают реализовать страницы свойств и сохраняемость свойств для элемента управления.

[COleControlModule](reference/colecontrolmodule-class.md)<br/>
Заменяет `CWinApp` класс для модуля управления OLE. Создайте класс, производный от `COleControlModule` класса, для разработки объекта модуля управления OLE. Он предоставляет функции элементов для инициализации модуля элемента управления OLE.

[COleControl](reference/colecontrol-class.md)<br/>
Создайте класс, производный от `COleControl` класса, для разработки элемента управления OLE. Производный от `CWnd` Этот класс наследует все функциональные возможности объекта окна Windows, а также дополнительные функции, относящиеся к OLE, такие как срабатывание событий и возможность поддержки методов и свойств.

[CConnectionPoint](reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint`Класс определяет особый тип интерфейса, используемый для взаимодействия с другими OLE-объектами, называемыми точкой соединения. Точка соединения реализует исходящий интерфейс, который может инициировать действия с другими объектами, такими как события обработки и уведомления об изменении.

[CPictureHolder](reference/cpictureholder-class.md)<br/>
Инкапсулирует функциональные возможности объекта изображения Windows и `IPicture` COM-интерфейса; используется для реализации пользовательского свойства изображения элемента управления OLE.

[CFontHolder](reference/cfontholder-class.md)<br/>
Инкапсулирует функциональные возможности объекта шрифта Windows и `IFont` COM-интерфейса; используется для реализации свойства «стандартный шрифт» элемента управления OLE.

[COlePropertyPage](reference/colepropertypage-class.md)<br/>
Отображает свойства элемента управления OLE в графическом интерфейсе аналогично диалоговому окну.

[CPropExchange](reference/cpropexchange-class.md)<br/>
Поддерживает реализацию сохраняемости свойств для элементов управления OLE. Аналог с [кдатаексчанже](reference/cdataexchange-class.md) для диалоговых окон.

[CMonikerFile](reference/cmonikerfile-class.md)<br/>
Принимает моникер или строковое представление, которое можно преобразовать в моникер, и выполняет синхронную привязку к потоку, для которого имя моникера является именем.

[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)<br/>
Работает аналогично `CMonikerFile` . Однако он привязывает моникер асинхронно к потоку, для которого имя моникера является именем.

[CDataPathProperty](reference/cdatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, которое можно загрузить асинхронно.

[CCachedDataPathProperty](reference/ccacheddatapathproperty-class.md)<br/>
Реализует свойство элемента управления OLE, асинхронно переданного и кэшированного в файле памяти.

[COleCmdUI](reference/colecmdui-class.md)<br/>
Позволяет активному документу принимать команды, происходящие в пользовательском интерфейсе контейнера (например, Филенев, Open, Print и т. д.), и позволяет контейнеру принимать команды, происходящие в пользовательском интерфейсе активного документа.

[COleSafeArray](reference/colesafearray-class.md)<br/>
Работает с массивами произвольного типа и измерения.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
