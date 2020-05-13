---
title: Контейнеры элементов управления ActiveX. Программирование элементов управления ActiveX в контейнере элементов управления ActiveX
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: 9620f4d47197147db4972c9f2024f6018a705902
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371186"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>Контейнеры элементов управления ActiveX. Программирование элементов управления ActiveX в контейнере элементов управления ActiveX

В этой статье описывается процесс доступа к открытым [методам](../mfc/mfc-activex-controls-methods.md) и [свойствам](../mfc/mfc-activex-controls-properties.md) встроенных элементов управления ActiveX.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

В принципе, вы будете следовать следующим шагам:

1. [Вставьте элемент управления ActiveX в контейнерный проект ActiveX](../mfc/inserting-a-control-into-a-control-container-application.md) с помощью Gallery.

1. [Определите переменную члена](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (или другую форму доступа) того же типа, что и класс обертки управления ActiveX.

1. [Программа управления ActiveX,](#_core_programming_the_activex_control) используя предопределенные функции членов класса обертки.

Для этого обсуждения предположим, что вы создали диалоговый проект (названный Контейнер) с поддержкой управления ActiveX. Контроль образца Circ, Circ, будет добавлен к результирующему проекту.

После того, как управление Circ будет вставлено в проект (шаг 1), вставьте экземпляр управления Circ в основной диалоговый ящик приложения.

## <a name="procedures"></a>Процедуры

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Добавление элемента управления Circ в шаблон диалога

1. Загрузите проект контейнера управления ActiveX. В этом примере `Container` используйте проект.

1. Нажмите на вкладку «Вид ресурсов».

1. Откройте папку **Dialog.**

1. Дважды щелкните основной шаблон диалогового окна. Для этого примера используйте **IDD_CONTAINER_DIALOG**.

1. Нажмите значок управления Circ на Toolbox.

1. Нажмите на место в диалоговом поле, чтобы вставить элемент управления Circ.

1. Из меню **файла** выберите **Сохранить все,** чтобы сохранить все изменения в шаблоне диалогового окна.

## <a name="modifications-to-the-project"></a>Изменения в проекте

Для обеспечения доступа приложения Контейнера к управлению Circ, Visual`CCirc`C'автоматически добавляет класс обертки () файл реализации (. CPP) к проекту контейнера и заголовок класса обертки (. H) файл в файл заголовка диалогового окна:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a>Заголовок класса Wrapper (. H) Файл

Чтобы получить и установить свойства (и вызвать методы) `CCirc` для управления Circ, класс обертки предоставляет декларацию всех открытых методов и свойств. В примере эти декларации содержатся в CIRC. H. Следующий пример представляет собой `CCirc` часть класса, которая определяет открытые интерфейсы управления ActiveX:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

Эти функции могут быть вызваны из других процедур приложения с помощью обычного синтаксиса СЗ. Для получения дополнительной информации об использовании этой функции элемента для [Programming the ActiveX control](#_core_programming_the_activex_control)доступа к методам и свойствам элемента управления см.

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a>Переменные изменения в проекте

После того, как элемент управления ActiveX был добавлен в проект и встроен в контейнер диалоговой коробки, к нему могут быть доступны другие части проекта. Самый простой способ получить доступ к элементу управления `CContainerDlg` — [создать переменную члена](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) класса диалогов (шаг 2), которая имеет тот же тип, что и класс обертки, добавленный в проект Visual C. Затем можно использовать переменную участника для доступа к встроенного элемента управления в любое время.

Когда **паралимпатор aAdd Member Variable** добавляет в проект переменную *m_circctl* члена, он также добавляет следующие строки в файл заголовка (. H) `CContainerDlg` класса:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

Кроме того, призыв к **DDX_Control** автоматически `CContainerDlg`добавляется `DoDataExchange`к реализации :

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a>Программирование управления ActiveX

На этом этапе вы вставили элемент управления ActiveX в шаблон диалога и создали для него переменную участника. Теперь для доступа к свойствам и методам встроенного элемента управления можно использовать общий синтаксис СЗЗ.

Как отмечено (в [Заголовок класса Wrapper (. H) Файл](#_core_the_wrapper_class_header_28h29_file)), файл заголовка (. H) для `CCirc` класса обертки, в данном случае CIRC. H, содержит список функций-членов, которые можно использовать для получения и установки любого выставленного значения свойства. Также доступны функции участника для открытых методов.

Общее место для изменения свойств элемента `OnInitDialog` управления находится в функции члена основного класса диалогов. Эта функция называется непосредственно перед попаданием в диалоговую будку и используется для инициализации его содержимого, включая любой из элементов управления.

В следующем примере кода используется переменная *m_circctl* члена для изменения свойств caption и CircleShape встроенного управления Circ:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>См. также раздел

[Контейнеры управления ActiveX](../mfc/activex-control-containers.md)
