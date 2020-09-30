---
title: Добавление класса MFC из библиотеки типов
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: 45bad00155cc1587980e6f3b25843a7a22e7e754
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503037"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов

Этот мастер используется для создания класса MFC из интерфейса в доступной библиотеке типов. Вы можете добавить класс MFC для [приложения MFC](../../mfc/reference/creating-an-mfc-application.md), [библиотеки DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md) или [элемента управления ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).

> [!NOTE]
> Вам не нужно создавать проект MFC с включенной автоматизацией для добавления класса из библиотеки типов.

Библиотека типов содержит двоичное описание интерфейсов, предоставляемых компонентом, определяющих методы, а также их параметры и возвращаемые типы. Библиотека типов должна быть зарегистрирована для отображения в списке **Доступные библиотеки типов** в мастере добавления классов из typelib.

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов

1. В **Обозреватель решений** или [представление классов](/visualstudio/ide/viewing-the-structure-of-code)щелкните правой кнопкой мыши имя проекта, в который нужно добавить класс.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В диалоговом окне [Добавление класса](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) в области Шаблоны щелкните **класс MFC из библиотеки типов**и нажмите кнопку **Открыть** , чтобы открыть [Мастер добавления класса из typelib](../../mfc/reference/add-class-from-typelib-wizard.md).

В мастере можно добавить более одного класса в библиотеку типов. Аналогичным образом можно добавлять классы из нескольких библиотек типов в одном сеансе мастера.

Мастер создает класс MFC, производный от [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавляемого из выбранной библиотеки типов. `COleDispatchDriver` реализует клиентскую сторону OLE Automation.

## <a name="see-also"></a>См. также раздел

[Клиенты автоматизации](../../mfc/automation-clients.md)<br/>
[Клиенты автоматизации: использование библиотек типов](../../mfc/automation-clients-using-type-libraries.md)
