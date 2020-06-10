---
title: Элементы управления ActiveX в MFC. События
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 129b805379fa68cb4f50ee1f8e3ac7d1b725d9ec
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622329"
---
# <a name="mfc-activex-controls-events"></a>Элементы управления ActiveX в MFC. События

Элементы управления ActiveX используют события для уведомления контейнера о том, что что-то произошло с элементом управления. Распространенными примерами событий являются щелчок на элементе управления, ввод данных с помощью клавиатуры и изменение состояния элемента управления. При возникновении этих действий элемент управления запускает событие для оповещения контейнера.

События также называются сообщениями.

MFC поддерживает два вида событий: акции и Custom. События на бирже — это события, которые класс [COleControl](reference/colecontrol-class.md) обрабатывает автоматически. Полный список событий хранения см. в статье [элементы управления ActiveX в MFC: Добавление событий акции](mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Пользовательские события позволяют элементу управления уведомлять контейнер, когда происходит действие, относящееся к этому элементу управления. Некоторые примеры могут быть изменены во внутреннем состоянии элемента управления или получении определенного сообщения окна.

Чтобы элемент управления активировал события должным образом, класс элемента управления должен сопоставлять каждое событие элемента управления с функцией-членом, которая должна вызываться при возникновении связанного события. Этот механизм сопоставления (называемый картой событий) централизует сведения о событии и позволяет Visual Studio легко обращаться к событиям элемента управления и управлять ими. Эта схема событий объявляется следующим макросом, расположенным в заголовке (. H) файл объявления класса элемента управления:

[!code-cpp[NVC_MFC_AxUI#2](codesnippet/cpp/mfc-activex-controls-events_1.h)]

После объявления схемы события она должна быть определена в реализации элемента управления (. CPP). Следующие строки кода определяют схему событий, позволяя элементу управления запускать определенные события:

[!code-cpp[NVC_MFC_AxUI#3](codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

Если для создания проекта используется мастер элементов ActiveX MFC, он автоматически добавляет эти строки. Если мастер элементов ActiveX MFC не используется, эти строки необходимо добавить вручную.

С помощью представление классов можно добавлять акции, поддерживаемые классом `COleControl` или пользовательскими событиями, которые вы определяете. Для каждого нового события представление классов автоматически добавляет соответствующую запись в карту событий элемента управления и элемент управления. IDL-файл.

В двух других статьях подробно рассматриваются события:

- [Элементы управления ActiveX в MFC. Добавление событий акции](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Элементы управления ActiveX в MFC. Добавление пользовательских событий](mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Методы](mfc-activex-controls-methods.md)<br/>
[Класс COleControl](reference/colecontrol-class.md)
