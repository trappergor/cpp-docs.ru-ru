---
title: Добавление класса MFC из библиотеки типов
ms.date: 11/04/2016
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
ms.openlocfilehash: bf9c763a215a4880d5b0ad206f6a347341fea9eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371725"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов

Используйте этот мастер для создания класса MFC из интерфейса в доступной библиотеке типов. Вы можете добавить класс MFC для [приложения MFC](../../mfc/reference/creating-an-mfc-application.md), [библиотеки DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md) или [элемента управления ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).

> [!NOTE]
> Вам не нужно создавать свой проект MFC с возможностью добавления класса из библиотеки типов.

Библиотека типов содержит двоичное описание интерфейсов, выставленных компонентом, определяя методы вместе с их параметрами и типами возврата. Библиотека вашего типа должна быть зарегистрирована, чтобы она отображалась в списке **доступных библиотек в** классе Добавления от Typelib Wizard. Дополнительную информацию можно узнать в библиотеке MSDN «Внутри распределенного COM: Тип библиотек и языковая интеграция».

### <a name="to-add-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов

1. В **любом виде решения** или [в классе View](/visualstudio/ide/viewing-the-structure-of-code), право нажмите правой кнопкой имя проекта, к которому вы хотите добавить класс.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В диалоговом окне [Add Class](../../ide/add-class-dialog-box.md) в панели шаблонов щелкните **mFC Class от Typelib,** а затем нажмите **Open,** чтобы отобразить [класс Добавления от Typelib Wizard.](../../mfc/reference/add-class-from-typelib-wizard.md)

В мастере можно добавить несколько классов в библиотеку типов. Кроме того, можно добавить классы из более чем одной библиотеки типов в одну сессию мастера.

Мастер создает класс MFC, полученный из [COleDispatchDriver,](../../mfc/reference/coledispatchdriver-class.md)для каждого интерфейса, который вы добавляете из выбранной библиотеки типов. `COleDispatchDriver`реализует клиентскую сторону автоматизации OLE.

## <a name="see-also"></a>См. также раздел

[Automation Clients](../../mfc/automation-clients.md)<br/>
[Клиенты автоматизации. Использование библиотек типов](../../mfc/automation-clients-using-type-libraries.md)
