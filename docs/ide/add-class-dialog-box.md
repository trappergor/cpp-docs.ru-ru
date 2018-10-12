---
title: Диалоговое окно "Добавление класса" | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.addclass
dev_langs:
- C++
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1eb848ae20ba9a587bfdf14881e1a3df3bbeb31
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420287"
---
# <a name="add-class-dialog-box"></a>Диалоговое окно "Добавление класса"

Диалоговое окно **Добавление класса** содержит шаблоны, которые позволяют выполнить следующие действия.

- Открыть соответствующий мастер создания кода, если он доступен. Дополнительные сведения см. в разделе [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md).

   \- или -

- Автоматически создать новый класс, добавив в проект соответствующие файлы и исходный код.

Перейти к диалоговому окну **Добавление класса** можно из меню **Проект**, **обозревателя решений** или [представления классов](/visualstudio/ide/viewing-the-structure-of-code).

> [!NOTE]
>  При попытке добавить класс, который не подходит для текущего проекта, вы получите сообщение об ошибке. Нажмите кнопку **ОК** , чтобы вернуться в диалоговое окно **Добавление класса** .

## <a name="add-class-templates"></a>Добавление шаблонов классов

Существует четыре категории шаблонов **добавления классов** : .NET, ATL, MFC и универсальные. При выборе шаблона в области **Шаблоны** текст, описывающий выбранный шаблон, появится в областях **Категории** и **Шаблоны** .

### <a name="net"></a>.NET

|Шаблон|Мастер|
|--------------|------------|
|Веб-служба ASP.NET;|Недоступно|
|Класс компонента (.NET)|Недоступно|
|Класс установщика (.NET)|Недоступно|
|Пользовательский элемент управления (.NET)|Недоступно|
|Форма Windows Forms (.NET)|Недоступно|

### <a name="atl"></a>ATL

|Шаблон|Мастер|
|--------------|------------|
|Добавление в MFC поддержки ATL|Недоступно|
|ASP-компонент библиотеки ATL|[Мастер ASP-компонента ATL](../atl/reference/atl-active-server-page-component-wizard.md)|
|Элемент управления ATL|[Мастер элементов управления ATL](../atl/reference/atl-control-wizard.md)|
|Диалог ATL|[Мастер диалоговых окон ATL](../atl/reference/atl-dialog-wizard.md)|
|Компонент COM+ 1.0 библиотеки ATL|[Мастер компонентов ATL COM+ 1.0](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|Потребитель OLEDB библиотеки ATL|[Мастер объекта-получателя OLE DB в ATL](../atl/reference/atl-ole-db-consumer-wizard.md)|
|Поставщик OLEDB библиотеки ATL|[Мастер поставщика OLE DB в ATL](../atl/reference/atl-ole-db-provider-wizard.md)|
|Свойства ATL|[Мастер страницы свойств ATL](../atl/reference/atl-property-page-wizard.md)|
|Простой объект ATL|[Мастер простых объектов ATL](../atl/reference/atl-simple-object-wizard.md)|
|Поставщик событий WMI|Мастер поставщика событий WMI|
|Поставщик экземпляров WMI|Мастер поставщика экземпляра WMI|

### <a name="mfc"></a>MFC

|Шаблон|Мастер|
|--------------|------------|
|Класс MFC|[Мастер добавления классов MFC](../mfc/reference/mfc-add-class-wizard.md)|
|Класс MFC из элемента управления ActiveX|[Мастер добавления классов из элемента ActiveX](../ide/add-class-from-activex-control-wizard.md)|
|Класс MFC из TypeLib|[Мастер добавления классов из библиотеки типов](../mfc/reference/add-class-from-typelib-wizard.md)|
|Потребитель ODBC MFC|[Мастер потребителя MFC ODBC](../mfc/reference/mfc-odbc-consumer-wizard.md)|

### <a name="generic-classes"></a>Универсальные классы

|Шаблон|Мастер|
|--------------|------------|
|Универсальный класс C++|[Мастер универсальных классов C++](../ide/generic-cpp-class-wizard.md)|

## <a name="see-also"></a>См. также

[Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)<br>
[Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Переопределение виртуальной функции](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)