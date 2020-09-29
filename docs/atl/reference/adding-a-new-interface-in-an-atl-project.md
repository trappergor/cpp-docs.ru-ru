---
title: Добавление нового интерфейса в проект ATL
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 8bf0138f85929e06b67e9a2e294eda8a2f385e1a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499387"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Добавление нового интерфейса в проект ATL

При добавлении интерфейса в объект или элемент управления создаются создана функции для каждого метода в этом интерфейсе. В объекте или элементе управления можно добавлять только интерфейсы, которые в настоящее время находятся в существующей библиотеке типов. Кроме того, класс, в который добавляется интерфейс, должен реализовывать макрос [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) или, если проект имеет атрибут, он должен иметь `coclass` атрибут.

Добавить новый интерфейс к элементу управления можно одним из двух способов: вручную или с помощью мастеров кода в представление классов.

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Использование мастеров кода в представление классов для добавления интерфейса в существующий объект или элемент управления

1. В [представление классов](/visualstudio/ide/viewing-the-structure-of-code)щелкните правой кнопкой мыши имя класса элемента управления. Например, полный или составной элемент управления или любой другой класс элементов управления, реализующий BEGIN_COM_MAP макрос в файле заголовка.

1. В контекстном меню выберите команду **Добавить**, а затем выберите команду **реализовать интерфейс**.

1. Выберите интерфейсы для реализации в [мастере реализации интерфейса](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard). Если интерфейс не существует ни в одной из доступных типов TypeLib, необходимо добавить его вручную в IDL-файл.

## <a name="to-add-a-new-interface-manually"></a>Добавление нового интерфейса вручную

1. Добавьте определение нового интерфейса в IDL-файл.

1. Наследование объекта или элемента управления от интерфейса.

1. Создайте новый [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) для интерфейса или, если проект имеет атрибут, добавьте `coclass` атрибут.

1. Реализуйте методы в интерфейсе.

## <a name="see-also"></a>См. также раздел

[Мастер проектов ATL](../../atl/reference/atl-project-wizard.md)<br/>
[Типы проектов C++ в Visual Studio](../../build/reference/visual-cpp-project-types.md)<br/>
[Программирование с помощью ATL и кода времени выполнения C](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Основы COM-объектов ATL](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Конфигурации проектов ATL по умолчанию](../../atl/reference/default-atl-project-configurations.md)
