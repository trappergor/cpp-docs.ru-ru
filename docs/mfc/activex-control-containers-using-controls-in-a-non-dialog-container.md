---
title: Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере без диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: b010c35f32462810cbdb008e5688d4b41254fad1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620764"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере без диалоговых окон

В некоторых приложениях, таких как приложения SDI или MDI, необходимо внедрить элемент управления в окно приложения. Функция **создания** члена класса-оболочки, вставленная Visual C++, может динамически создавать экземпляр элемента управления без необходимости в диалоговом окне.

Функция **создания** члена имеет следующие параметры:

*лпсзвиндовнаме*<br/>
Указатель на текст, отображаемый в свойстве Text или Caption элемента управления (если имеется).

*двстиле*<br/>
Стили Windows. Полный список см. в разделе [CWnd:: CreateControl](reference/cwnd-class.md#createcontrol).

*rect*<br/>
Задает размер и расположение элемента управления.

*ппарентвнд*<br/>
Указывает родительское окно элемента управления, обычно `CDialog` . Оно не должно иметь **значение NULL**.

*nID*<br/>
Указывает идентификатор элемента управления и может использоваться контейнером для ссылки на элемент управления.

Одним из примеров использования этой функции для динамического создания элемента управления ActiveX может быть представление формы приложения SDI. Затем можно создать экземпляр элемента управления в `WM_CREATE` обработчике приложения.

В этом примере `CMyView` является основным классом представления, `CCirc` является классом-оболочкой и Circ. H — это заголовок (. H) файл класса-оболочки.

Реализация этой функции состоит из четырех этапов.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Динамическое создание элемента управления ActiveX в окне, не являющемся диалоговым окном

1. Вставка CIRC. H в КМИВИЕВ. З, непосредственно перед `CMyView` определением класса:

   [!code-cpp[NVC_MFC_AxCont#12](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. Добавьте переменную-член (типа `CCirc` ) в защищенный раздел `CMyView` определения класса, расположенного в кмивиев. Высоты

   [!code-cpp[NVC_MFC_AxCont#13](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. Добавьте `WM_CREATE` обработчик сообщений в класс `CMyView` .

1. В функции обработчика выполните `CMyView::OnCreate` вызов функции элемента управления, `Create` используя **этот** указатель в качестве родительского окна:

   [!code-cpp[NVC_MFC_AxCont#15](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. Выполните повторную сборку проекта. Элемент управления Circ будет создан динамически при создании представления приложения.

## <a name="see-also"></a>См. также раздел

[Контейнеры элементов управления ActiveX](activex-control-containers.md)
