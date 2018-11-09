---
title: Добавление свойства (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
ms.openlocfilehash: 3c47a5b50442f47e6042ea1232590dbdde7299ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563089"
---
# <a name="adding-a-property-visual-c"></a>Добавление свойства (Visual C++)

Вы можете использовать [мастер добавления свойства](../ide/names-add-property-wizard.md) для добавления свойства в интерфейс в проекте.

### <a name="to-add-a-property-to-your-object"></a>Добавление свойства в объект

1. В [представлении классов](/visualstudio/ide/viewing-the-structure-of-code) щелкните правой кнопкой мыши имя интерфейса, в который нужно добавить свойство.

   > [!NOTE]
   > Вы также можете добавлять свойства в disp-интерфейсы, которые, если только проект не имеет атрибуты, вложены в узел библиотеки.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить свойство**.

1. В [мастере добавления свойства](../ide/names-add-property-wizard.md) укажите сведения для создания свойства.

1. Задайте параметры IDL для этого свойства на странице [Атрибуты IDL](../ide/idl-attributes-add-property-wizard.md) мастера.

1. Нажмите кнопку **Готово**, чтобы добавить свойство.

Методы **Get** и `Put` свойства отображаются в представлении классов в виде двух значков под интерфейсом, в котором оно определено. Можно дважды щелкнуть любой значок, чтобы просмотреть объявление свойства в IDL-файле.

- Для интерфейсов ATL функции **Get** и **Put** добавляются в CPP-файл, а ссылки на эти функции — в H-файл.

- Для disp-интерфейсов MFC, если выбран тип реализации **Переменная-член**, метод и переменная добавляются в класс, который его реализует. Если выбрать **методы Get/Set** в качестве типа реализации, два метода добавляются в класс, который его реализует.

## <a name="see-also"></a>См. также

[Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)<br>
[Редактирование интерфейса COM](../ide/editing-a-com-interface.md)<br>
[Модель COM](/windows/desktop/com/the-component-object-model)<br>
[Указатели интерфейса и интерфейсы](/windows/desktop/com/interface-pointers-and-interfaces)