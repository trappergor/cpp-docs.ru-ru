---
title: 'Элементы ActiveX в MFC: Использование привязки данных в элемент управления ActiveX | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 397356f8144e3680f3b2d19824d19c0a3bbaddd1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062617"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>Элементы управления ActiveX в MFC. Использование привязки данных в элементе управления ActiveX

Одним из более мощные использования элементов ActiveX является привязка данных, что позволяет свойства элемента управления для привязки с определенным полем в базе данных. Когда пользователь изменяет данные в этом связанное свойство, элемент управления уведомляет базы данных и запросов, что обновить поле записи. Базы данных уведомляет элемент управления успех или сбой запроса.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, которые следуют за ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

В этой статье рассматриваются задачи на стороне элемента управления. Реализация взаимодействия привязки данных с базой данных отвечает за контейнера элемента управления. Как управлять взаимодействие с базой данных в контейнере выходит за рамки данной документации. В оставшейся части этой статьи объясняется способ подготовки элемента управления для привязки данных.

![Концептуальная схема данных&#45;связанного элемента управления](../mfc/media/vc374v1.gif "vc374v1") концептуальная схема элемента управления с привязкой данных

`COleControl` Класс предоставляет две функции-члены, которые делают просто реализовать привязку данных. Первая функция, [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), используемый для запроса разрешения на изменение значения свойства. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), вторая функция вызывается после успешного изменения значения свойства.

В этой статье рассматриваются следующие темы:

- [Создание стандартного привязываемые свойства](#vchowcreatingbindablestockproperty)

- [Создание метода привязки Get и Set](#vchowcreatingbindablegetsetmethod)

##  <a name="vchowcreatingbindablestockproperty"></a> Создание стандартного привязываемые свойства

Имеется возможность создать стандартное свойство с привязкой к данным, несмотря на то, что более вероятно, что вы будете [метод привязываемых get и set](#vchowcreatingbindablegetsetmethod).

> [!NOTE]
>  Стандартные свойства имеют `bindable` и `requestedit` атрибуты по умолчанию.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Чтобы добавить возможности связывания стандартное свойство с помощью мастера добавления свойства

1. Начать проект с использованием [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md).

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления.

   Откроется контекстное меню.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **добавить свойство**.

1. Выберите одну из записей из **имя свойства** стрелку раскрывающегося списка. Например, можно выбрать **текст**.

   Так как **текст** стандартное свойство **bindable** и **requestedit** атрибуты отмечены флажками.

1. Установите следующие флажки из **атрибуты IDL** вкладку: **displaybind** и **defaultbind** добавить атрибуты к определению свойств в проекте. IDL-файла. Эти атрибуты сделать элемент управления видимым для пользователя и сделать стандартное свойство свойство привязки по умолчанию.

На этом этапе ваш элемент управления может отображать данные из источника данных, но пользователь не сможет обновить поля данных. Если требуется элемент управления также иметь возможность обновления данных, изменения `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) функции для поиска следующим образом:

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Теперь можно создать проект, который будет зарегистрировать элемент управления. При вставке элемента управления в диалоговом окне **поля данных** и **источника данных** будут добавлены свойства, и теперь вы можете выбрать источник данных и поле для отображения в элементе управления.

##  <a name="vchowcreatingbindablegetsetmethod"></a> Создание метода привязки Get и Set

Помимо привязанный к данным метод get и set, можно также создать [привязываемых стандартное свойство](#vchowcreatingbindablestockproperty).

> [!NOTE]
>  Подразумевается, что у вас есть элемент управления ActiveX проекта который наследуется от элемента управления Windows.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Чтобы добавить метод привязываемых get и set, с помощью мастера добавления свойства

1. Загрузите проект элемента управления.

1. На **параметры управления** выберите класс окна для элемента управления в подкласс. Например можно создать подкласс элемента управления.

1. Загрузите проект элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления.

   Откроется контекстное меню.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **добавить свойство**.

1. Введите имя свойства в **имя свойства** поле. Используйте `MyProp` для этого примера.

1. Выберите тип данных из **тип свойства** поле с раскрывающимся списком. Используйте **короткие** для этого примера.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

9. Установите следующие флажки на вкладке "атрибуты IDL": **bindable**, **requestedit**, **displaybind**, и **defaultbind** для добавления атрибуты для определения свойства в проекте. IDL-файла. Эти атрибуты сделать элемент управления видимым для пользователя и сделать стандартное свойство свойство привязки по умолчанию.

10. Нажмите кнопку **Готово**.

11. Изменить текст `SetMyProp` работать так, чтобы он содержал следующий код:

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

12. Параметр, передаваемый `BoundPropertyChanged` и `BoundPropertyRequestEdit` "функции" — идентификатор dispid свойства, который является параметром, передаваемая атрибуту id() для свойства. IDL-файла.

13. Изменить [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) , поэтому он содержит следующий код:

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

14. Изменить `OnDraw` работать так, чтобы он содержал следующий код:

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

15. В раздел public файла заголовка файла заголовка для класса элемента управления добавьте следующие определения переменных-членов (конструкторы):

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

16. Сделать следующую строку в последней строке `DoPropExchange` функции:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

17. Изменить `OnResetState` работать так, чтобы он содержал следующий код:

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

18. Изменить `GetMyProp` работать так, чтобы он содержал следующий код:

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Теперь можно создать проект, который будет зарегистрировать элемент управления. При вставке элемента управления в диалоговом окне **поля данных** и **источника данных** будут добавлены свойства, и теперь вы можете выбрать источник данных и поле для отображения в элементе управления.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

