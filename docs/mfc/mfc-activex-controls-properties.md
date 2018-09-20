---
title: 'Элементы управления MFC ActiveX: Свойства | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27cdbd548366bcf02e2d6282b309402cf25af2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401619"
---
# <a name="mfc-activex-controls-properties"></a>Элементы управления ActiveX в MFC. Свойства

Элемент управления ActiveX создает события для взаимодействия со своим контейнером для элемента управления. Контейнер, в ответ использует методы и свойства для взаимодействия с элементом управления. Методы и свойства похожи и цели, соответственно, для функции-члены и переменные-члены класса C++. Свойства являются элементами данных элемента управления ActiveX, которые имеют доступ к любому контейнеру. Свойства обеспечивают интерфейс для приложений, содержащих элементы управления ActiveX, таких как клиенты автоматизации, а также контейнеры элементов управления ActiveX.

Свойства также называются атрибуты.

Дополнительные сведения о методах управления ActiveX см. в статье [элементы ActiveX в MFC: методы](../mfc/mfc-activex-controls-methods.md).

Элементы ActiveX можно реализовать, биржевая и пользовательских методов и свойств. Класс `COleControl` предоставляет реализацию для стандартных свойств. (Полный список стандартных свойств, см. в статье [элементы ActiveX в MFC: Добавление свойства запасов](../mfc/mfc-activex-controls-adding-stock-properties.md).) Пользовательские свойства, определяемые разработчиком, добавьте в элемент управления ActiveX специальные возможности. Дополнительные сведения см. в разделе [элементы ActiveX в MFC: Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md).

Как пользовательские, так и стандартных свойств, как и методы, поддерживаются с помощью механизма, который состоит из схема подготовки к отправке, который обрабатывает свойства, методы и существующие функции-члены `COleControl` класса. Кроме того эти свойства могут иметь параметры, которые разработчик использует для передачи дополнительных сведений в элемент управления.

В следующих статьях рассматриваются свойства элемента управления ActiveX, более подробно:

- [Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Элементы ActiveX в MFC. Добавление пользовательских свойств](../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Элементы ActiveX в MFC. Реализация расширенных свойств](../mfc/mfc-activex-controls-advanced-property-implementation.md)

- [Элементы ActiveX в MFC. Доступ к внешним свойствам](../mfc/mfc-activex-controls-accessing-ambient-properties.md)

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

