---
title: Элементы управления ActiveX в MFC. Создание сервера автоматизации
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
ms.openlocfilehash: f2c941e43e810845560b4c35c558ec70248c21ed
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622384"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>Элементы управления ActiveX в MFC. Создание сервера автоматизации

Можно разработать элемент управления ActiveX MFC как сервер автоматизации для программного внедрения этого элемента управления в другое приложение и вызова методов в элементе управления из приложения. Такой элемент управления по-прежнему будет доступен для размещения в контейнере элементов управления ActiveX.

### <a name="to-create-a-control-as-an-automation-server"></a>Создание элемента управления в качестве сервера автоматизации

1. [Создайте](reference/mfc-activex-control-wizard.md) элемент управления.

1. [Добавьте методы](mfc-activex-controls-methods.md).

1. Переопределите [исинвокеалловед](reference/colecontrol-class.md#isinvokeallowed).

1. Создайте элемент управления.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Программный доступ к методам на сервере автоматизации

1. Создайте приложение, например [исполняемый файл MFC](reference/mfc-application-wizard.md).

1. В начале `InitInstance` функции добавьте следующую строку:

   [!code-cpp[NVC_MFC_AxCont#17](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. В представление классов щелкните правой кнопкой мыши узел проекта и выберите **Добавить класс из typelib** , чтобы импортировать библиотеку типов.

   В проект будут добавлены файлы с расширением h и CPP.

1. В файле заголовка класса, в котором будет вызываться один или несколько методов в элементе управления ActiveX, добавьте следующую строку: `#include filename.h` , где имя файла — это имя файла заголовка, который был создан при импорте библиотеки типов.

1. В функции, в которой вызов метода в элементе управления ActiveX выполняется, добавьте код, который создает объект класса оболочки элемента управления и создает объект ActiveX. Например, следующий код MFC создает экземпляр `CCirc` элемента управления, получает свойство Caption и отображает результат при нажатии кнопки ОК в диалоговом окне:

   [!code-cpp[NVC_MFC_AxCont#18](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

Если добавить методы в элемент управления ActiveX после его использования в приложении, можно приступить к использованию последней версии элемента управления в приложении, удалив файлы, созданные при импорте библиотеки типов. Затем снова импортируйте библиотеку типов.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)
