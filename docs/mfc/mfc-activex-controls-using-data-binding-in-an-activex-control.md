---
title: Элементы управления ActiveX в MFC. Использование привязки данных в элементе управления ActiveX
ms.date: 11/19/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: 41ac0180242aea3143a1df2c32dc81fb18cd7dca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370780"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>Элементы управления ActiveX в MFC. Использование привязки данных в элементе управления ActiveX

Одним из наиболее мощных применений элементов управления ActiveX является связывание данных, что позволяет свойству элемента управления связываться с определенным полем в базе данных. Когда пользователь изменяет данные в этом связанном свойстве, элемент управления уведомляет базу данных и просит обновить поле записи. Затем база данных уведомляет о контроле за успехом или неудачей запроса.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

Эта статья охватывает контрольную сторону вашей задачи. Реализация связывающих взаимодействий с базой данных является обязанностью контрольного контейнера. Управление взаимодействиями баз данных в контейнере выходит за рамки данной документации. Как вы готовите элемент управления для связывания данных, объясняется в остальной части этой статьи.

![Концептуальная диаграмма данных&#45;связанного контроля](../mfc/media/vc374v1.gif "Концептуальная диаграмма данных&#45;связанного контроля") <br/>
Концептуальная диаграмма управления связанными данными

Класс `COleControl` предоставляет две функции члена, которые делают связывание данных простым процессом для реализации. Первая функция, [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), используется для запроса разрешения на изменение значения свойства. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), вторая функция, называется после того, как значение свойства было успешно изменено.

В этой статье рассматриваются следующие темы:

- [Создание связующего свойства фонда](#vchowcreatingbindablestockproperty)

- [Создание связываемого метода получения/установки](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a>Создание связующего свойства фонда

Можно создать свойство склада, привязанного к данным, хотя более вероятно, что вам потребуется [связный метод получения/набора.](#vchowcreatingbindablegetsetmethod)

> [!NOTE]
> Свойства стока `bindable` `requestedit` имеют атрибуты и атрибуты по умолчанию.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Добавить связываемое свойство с запасом с помощью Мастера свойств Добавления

1. Начните проект с помощью [MFC ActiveX Control Wizard.](../mfc/reference/mfc-activex-control-wizard.md)

1. Нажмите правой кнопкой интерфейса узла для вашего управления.

   Это открывает меню ярлыка.

1. Из меню ярлыка, нажмите **Добавить,** а затем нажмите **Добавить свойство**.

1. Выберите одну из записей из списка выпадающих названий **недвижимости.** Например, можно выбрать **текст**.

   Поскольку **Text** является свойством акций, **атрибуты bindable** и **requestedit** уже проверяются.

1. Выберите следующие флажки из **вкладки IDL Attributes:** **displaybind** и **defaultbind,** чтобы добавить атрибуты в определение свойства в проекте. IdL файл. Эти атрибуты делают элемент управления видимым для пользователя и делают свойство запаса связуемым свойством по умолчанию.

На этом этапе элемент управления может отображать данные из источника данных, но пользователь не сможет обновлять поля данных. Если вы хотите, чтобы ваш элемент управления `OnOcmCommand` также мог обновлять данные, измените функцию [OnOcmCommand,](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) чтобы выглядеть следующим образом:

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Теперь можно построить проект, который будет регистрировать элемент управления. При вставке элемента управления в диалоговое поле будут добавлены свойства **поля данных** и **источника данных,** и теперь можно выбрать источник данных и поле для отображения в элементе управления.

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a>Создание связываемого метода получения/установки

В дополнение к методу получения/набора данных, вы также можете создать [связываемое свойство склада.](#vchowcreatingbindablestockproperty)

> [!NOTE]
> Эта процедура предполагает, что у вас есть проект управления ActiveX, который подклассирует управление Windows.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Добавить связываемый метод получения/набора с помощью мастера свойств Добавления

1. Загрузите проект элемента управления.

1. На странице **"Настройки управления"** выберите класс окон для подкласса управления. Например, можно подклассифицировать элемент управления EDIT.

1. Загрузите проект элемента управления.

1. Нажмите правой кнопкой интерфейса узла для вашего управления.

   Это открывает меню ярлыка.

1. Из меню ярлыка, нажмите **Добавить,** а затем нажмите **Добавить свойство**.

1. Введите имя свойства в поле **имени свойства.** Используйте `MyProp` для этого примера.

1. Выберите тип данных из окна списка выпадающих данных **типа свойства.** Используйте **кратко для** этого примера.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

1. Выберите следующие флажки из вкладки IDL Атрибуты: **bindable,** **requestedit,** **displaybind**и **defaultbind,** чтобы добавить атрибуты к определению свойства в проекте. IdL файл. Эти атрибуты делают элемент управления видимым для пользователя и делают свойство запаса связуемым свойством по умолчанию.

1. Нажмите кнопку **Готово**.

1. Измените тело `SetMyProp` функции так, чтобы она содержит следующий код:

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. Параметр, передаваемый `BoundPropertyChanged` и `BoundPropertyRequestEdit` функции является dispid свойства, который является параметром, переданным id () атрибут для свойства в . IdL файл.

1. Измените функцию [OnOcmCommand,](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) чтобы она содержит следующий код:

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. Измените `OnDraw` функцию так, чтобы она содержащая следующий код:

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. В общедоступный раздел файла заголовка файл заголовка для класса управления добавьте следующие определения (конструкторы) для переменных членов:

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. Сделайте следующую строку `DoPropExchange` последней строкой в функции:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. Измените `OnResetState` функцию так, чтобы она содержащая следующий код:

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. Измените `GetMyProp` функцию так, чтобы она содержащая следующий код:

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Теперь можно построить проект, который будет регистрировать элемент управления. При вставке элемента управления в диалоговое поле будут добавлены свойства **поля данных** и **источника данных,** и теперь можно выбрать источник данных и поле для отображения в элементе управления.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)
