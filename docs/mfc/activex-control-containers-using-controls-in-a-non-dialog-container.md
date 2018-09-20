---
title: 'Контейнеры элементов управления ActiveX: Использование элементов управления в контейнере без диалоговых окон | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a20d069024fd424beeec41d3483f8e2c28432e00
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410732"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>Контейнеры элементов управления ActiveX. Использование элементов управления в контейнере без диалоговых окон

В некоторых приложений, таких как приложении SDI или MDI-приложения требуется внедрить элемент управления в окне приложения. **Создать** функции-члена класса-оболочки, вставленные Visual C++, можно создать экземпляр элемента управления динамически, без необходимости для диалогового окна.

**Создать** функция-член имеет следующие параметры:

*lpszWindowName*<br/>
Указатель на текст, который отображается в свойстве Text или Caption элемента управления (если таковые имеются).

*dwStyle*<br/>
Стили Windows. Полный список см. в разделе [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol).

*Rect*<br/>
Задает размер и положение элемента управления.

*pParentWnd*<br/>
Указывает родительскому окну элемента управления, обычно `CDialog`. Он не должен быть **NULL**.

*nID*<br/>
Указывает идентификатор элемента управления и может использоваться в качестве контейнера для ссылки на элемент управления.

В представлении формы приложения SDI будет одним из примеров применения этой функции для динамического создания элемента управления ActiveX. Затем можно создать экземпляр элемента управления в `WM_CREATE` обработчика приложения.

В этом примере `CMyView` является класс основное представление, `CCirc` — класс-оболочка и круглый H — это заголовок (. H) файл класса-оболочки.

Реализация этой возможности — это процесс четыре шага.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Для динамического создания элемента управления ActiveX в окне без диалоговых окон

1. Вставить круглый H в CMYVIEW. H, непосредственно перед `CMyView` определение класса:

     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. Добавьте переменную-член (типа `CCirc`) в защищенный раздел `CMyView` в CMYVIEW определение класса. H:

     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. Добавить `WM_CREATE` обработчик сообщений для класса `CMyView`.

1. В функции обработчика `CMyView::OnCreate`, вызовите элемент управления `Create` функцию при помощи **это** указатель в виде родительского окна:

     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. Перестройте проект. Элемент управления Кр создается динамически при каждом создании представления приложения.

## <a name="see-also"></a>См. также

[Контейнеры для элементов ActiveX](../mfc/activex-control-containers.md)

