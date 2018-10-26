---
title: 'Элементы ActiveX в MFC: Создание сервера автоматизации | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e37e6183ca840067ceca47dd48f3b24d7b3b98c7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074544"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>Элементы управления ActiveX в MFC. Создание сервера автоматизации

Вы можете разрабатывать элемента управления MFC ActiveX как сервера автоматизации для программного включения этого элемента управления в другом приложении и вызов методов в элементе управления из приложения. Такой элемент управления по-прежнему доступен для размещения в контейнере элементов управления ActiveX.

### <a name="to-create-a-control-as-an-automation-server"></a>Создание элемента управления как сервера автоматизации

1. [Создание](../mfc/reference/mfc-activex-control-wizard.md) элемента управления.

1. [Добавьте методы](../mfc/mfc-activex-controls-methods.md).

1. Переопределить [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed).

1. Создание элемента управления.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Для программного доступа к методам в сервер автоматизации

1. Создание приложения, например, [MFC exe](../mfc/reference/mfc-application-wizard.md).

1. В начале `InitInstance` функции, добавьте следующую строку:

   [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. В представлении классов щелкните правой кнопкой мыши узел проекта и выберите **добавления классов из typelib** импорт библиотеки типов.

   Это добавит файлы с .cpp и .h расширения имени файла в проект.

1. В файле заголовка класса, где будет вызываться один или несколько методов в элементе управления ActiveX, добавьте следующую строку: `#include filename.h`, где имя файла — это имя файла заголовка, который был создан во время импорта библиотеки типов.

1. В функции, где будет вызов метода в элементе управления ActiveX добавьте код, создающий объект класса-оболочки элемента управления и создать объект ActiveX. Например, следующий код MFC создает `CCirc` Получает свойство заголовка элемента управления и отображает результат, когда нажата кнопка ОК в диалоговом окне:

   [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

При добавлении методов элемента управления ActiveX после использования его в приложении, можно начать использовать последнюю версию элемента управления в приложении, удалив файлы, которые были созданы при импорте библиотеки типов. Затем импортируйте библиотеку типов.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

