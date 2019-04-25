---
title: Элементы ActiveX в MFC. Свойства
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
ms.openlocfilehash: 5e01854e7ae7acdc33275351d0d26a76dfeabc9b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324328"
---
# <a name="mfc-activex-controls-properties"></a>Элементы ActiveX в MFC. Свойства

Элемент управления ActiveX создает события для взаимодействия со своим контейнером для элемента управления. Контейнер, в ответ использует методы и свойства для взаимодействия с элементом управления. Методы и свойства похожи и цели, соответственно, для функции-члены и переменные-члены класса C++. Свойства являются элементами данных элемента управления ActiveX, которые имеют доступ к любому контейнеру. Свойства обеспечивают интерфейс для приложений, содержащих элементы управления ActiveX, таких как клиенты автоматизации, а также контейнеры элементов управления ActiveX.

Свойства также называются атрибуты.

Дополнительные сведения о методах управления ActiveX см. в статье [элементы управления MFC ActiveX: Методы](../mfc/mfc-activex-controls-methods.md).

Элементы ActiveX можно реализовать, биржевая и пользовательских методов и свойств. Класс `COleControl` предоставляет реализацию для стандартных свойств. (Полный список стандартных свойств, см. в статье [элементы управления MFC ActiveX: Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md).) Пользовательские свойства, определяемые разработчиком, добавьте в элемент управления ActiveX специальные возможности. Дополнительные сведения см. в разделе [элементы управления MFC ActiveX: Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md).

Как пользовательские, так и стандартных свойств, как и методы, поддерживаются с помощью механизма, который состоит из схема подготовки к отправке, который обрабатывает свойства, методы и существующие функции-члены `COleControl` класса. Кроме того эти свойства могут иметь параметры, которые разработчик использует для передачи дополнительных сведений в элемент управления.

В следующих статьях рассматриваются свойства элемента управления ActiveX, более подробно:

- [Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Элементы ActiveX в MFC. Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Элементы ActiveX в MFC. Реализация расширенных свойств](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [Элементы ActiveX в MFC. Доступ к свойствам окружения](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)
