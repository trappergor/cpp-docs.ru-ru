---
title: Внешний вид, мастер элементов управления ATL
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 3484fb5d0f919af0dfd18b584e96d4675e2baea8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319398"
---
# <a name="appearance-atl-control-wizard"></a>Внешний вид, мастер элементов управления ATL

Используйте эту страницу мастера для определения дополнительных параметров элемента пользователя для управления. Эта страница доступна для элементов управления, идентифицированных как **стандартные элементы управления** под **типом управления** на странице [Options, ATL Control Wizard.](../../atl/reference/options-atl-control-wizard.md)

## <a name="uielement-list"></a>Список элементов пользовательского интерфейса

- **Просмотр состояния**

   Устанавливает внешний вид элемента управления внутри контейнера.

  - **Непрозрачный:** Устанавливает VIEWSTATUS_OPAQUE бит в перечислении [VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus) и рисует весь прямоугольник управления, передаваемый [в CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw) метод. Элемент управления выглядит полностью непрозрачным, и ни один из контейнеров не отображается за границами управления.

      Эта настройка помогает контейнеру быстрее нарисовать элемент управления. Если этот параметр не выбран, элемент управления может содержать прозрачные части.

      Только непрозрачный элемент управления может иметь сплошной фон.

  - **Твердый фон**: Устанавливает VIEWSTATUS_SOLIDBKGND бит в пересчете VIEWSTATUS. Фон элемента управления отображается как сплошной цвет без шаблона.

      Эта опция доступна только в том случае, если выбран опция **Opaque.**

- **Добавление элемента управления на основе**

   Устанавливает элемент управления, основанный на типе управления Windows, добавляя в класс элемент данных [CContainedWindow,](ccontainedwindowt-class.md) реализующий элемент управления. Он также добавляет карту сообщений и функции обработчика сообщений для обработки сообщений Windows для управления. Выберите из списка тип управления Windows, который вы хотите создать, если таковые имеется.

  - **Кнопку**

  - **ListBox**

  - **SysAnimate32**

  - **SysListView32**

  - **ComboBox**

  - **Richedit**

  - **SysDateTimePick32**

  - **SysMonthCal32**

  - **ComboBoxEx32**

  - **ScrollBar**

  - **SysHeader32**

  - **SysTabControl32**

  - **Изменить**

  - **Статический**

  - **SysIPAddress32**

  - **SysTreeView32**

- **Статус Misc**

   Устанавливает дополнительные параметры внешнего вида и поведения для элемента управления.

  - **Невидимый во время выполнения:** Устанавливает элемент управления, чтобы быть невидимым во время выполнения. Можно использовать невидимые элементы управления для выполнения операций в фоновом режиме, таких как события стрельбы с интервалами.

  - **Действия, как кнопка**: Устанавливает OLEMISC_ACTSLIKEBUTTON бит в перечислении [OLEMISC,](/windows/win32/api/oleidl/ne-oleidl-olemisc) чтобы элемент управления действовать как кнопка. Если контейнер пометил клиентский сайт управления как кнопку по умолчанию, выбор этой опции позволяет элементу управления кнопкой отображатьсебя в качестве кнопки по умолчанию, рисуя себя более толстой рамкой. Смотрите [CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault) для получения дополнительной информации.

  - **Действия, как этикетка**: Устанавливает OLEMISC_ACTSLIKELABEL бит в перечислении OLEMISC, чтобы контроль заменить родной этикетке контейнера. Контейнер определяет, что делать с этим флагом, если что- ное.

- **Прочее**

   Устанавливает дополнительные параметры поведения для элемента управления.

  - **Нормализованный DC**: Устанавливает элемент управления для создания нормализованного контекста устройства, когда он вызывается, чтобы нарисовать себя. Это действие стандартизирует внешний вид элемента управления, но делает рисунок менее эффективным.

  - **Только окно**: Указывает, что ваш элемент управления не может быть без окон. Если вы не выберете эту опцию, ваш элемент управления автоматически не имеет окон в контейнерах, поддерживающих объекты без окон, и автоматически оконируется в контейнерах, не поддерживающих объекты без окон. Выбор этой опции заставляет ваш элемент управления быть оконным окном, даже в контейнерах, которые поддерживают объекты без окон.

  - **Вставка**: Выберите эту опцию, чтобы ваш контроль отображался в диалоговом окне **вставки объектов** приложений, таких как Word и Excel. Управление может быть вставлено любым приложением, которое поддерживает встроенные объекты через это диалоговое окно.

## <a name="see-also"></a>См. также раздел

[Мастер элементов управления ATL](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT Образец: Суперклассы Стандартный контроль Windows](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
