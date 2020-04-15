---
title: Изменение стилей окна, созданного MFC
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
ms.openlocfilehash: 221092eb25a4f044cda5b379d6774659d9e9d2d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374590"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Изменение стилей окна, созданного MFC

В своей `WinMain` версии функции, MFC регистрирует несколько стандартных классов окна для вас. Поскольку обычно вы не отослалиm `WinMain`iFC, эта функция не дает вам возможности изменить стили окон MFC по умолчанию. В этой статье объясняется, как можно изменить стили такого предварительно зарегистрированного класса окон в существующем приложении.

## <a name="changing-styles-in-a-new-mfc-application"></a><a name="_core_changing_styles_in_a_new_mfc_application"></a>Изменение стилей в новом приложении MFC

Если вы используете Visual C'2.0 или позже, вы можете изменить стили окнов по умолчанию в «Мастере приложения» при создании приложения. На странице пользовательских функций пользовательского интерфейса «Приложение Мастера» можно изменить стили для окна основного кадра и детских окон MDI. Для любого типа окна можно указать толщину кадра (толстую или тонкую) и любой из следующих:

- Имеет ли окно элементы минимизации или максимизации элементов управления.

- Кажется ли окно изначально сведенным к минимуму, максимизировано, или ни то, ни другое.

Для окон основной рамы можно также указать, есть ли в окне меню системы. Для дочерних окон MDI можно указать, поддерживает ли окно сплиттерные стекла.

## <a name="changing-styles-in-an-existing-application"></a><a name="_core_changing_styles_in_an_existing_application"></a>Изменение стилей в существующем приложении

Если вы меняете атрибуты окна в существующем приложении, следуйте инструкциям в остальной части этой статьи.

Чтобы изменить атрибуты окна по умолчанию, используемые фробтворным приложением, созданным с помощью мастера приложения, переопределить функцию виртуального члена [preCreateWindow.](../mfc/reference/cwnd-class.md#precreatewindow) `PreCreateWindow`позволяет приложению получить доступ к процессу создания, обычно управляемому внутри класса [CDocTemplate.](../mfc/reference/cdoctemplate-class.md) Фреймов вызывает `PreCreateWindow` непосредственно перед созданием окна. Изменяя переданную структуру `PreCreateWindow` [CREATESTRUCT,](/windows/win32/api/winuser/ns-winuser-createstructw) приложение может изменить атрибуты, используемые для создания окна. Например, чтобы убедиться, что окно не использует заголовок, используйте следующую операцию:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

В примере приложения [CTRLBARS](../overview/visual-cpp-samples.md) демонстрируется этот метод изменения атрибутов окна. В зависимости от `PreCreateWindow`того, в чем изменяется приложение, может потребоваться назвать реализацию функции базовым классом.

Следующее обсуждение охватывает дело SDI и [дело MDI](#_core_the_mdi_case).

## <a name="the-sdi-case"></a><a name="_core_the_sdi_case"></a>Дело SDI

В одном приложении интерфейса документа (SDI) стиль окна по умолчанию представляет собой сочетание **WS_OVERLAPPEDWINDOW** и **FWS_ADDTOTITLE** стилей. **FWS_ADDTOTITLE** — это стиль MFC, который инструктирует платформу для добавления заголовка документа в заголовок окна. Чтобы изменить атрибуты окна в приложении SDI, переопределить `PreCreateWindow` функцию в вашем классе, полученную из `CFrameWnd` (который называет `CMainFrame`мастер приложения). Пример:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Этот код создает окно основной кадр без коннопок Минимизации и Максима и без значительной границы. Окно изначально центрируется на экране.

## <a name="the-mdi-case"></a><a name="_core_the_mdi_case"></a>Дело MDI

Требуется немного больше работы, чтобы изменить стиль окна окна детского окна в приложении с несколькими документами интерфейса (MDI). По умолчанию приложение MDI, созданное с помощью Мастера приложения, использует класс [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) по умолчанию, определенный в MFC. Чтобы изменить стиль окна окна детского окна MDI, `CMDIChildWnd` необходимо получить новый `CMDIChildWnd` класс и заменить все ссылки на в проекте ссылками на новый класс. Скорее всего, единственная ссылка `CMDIChildWnd` в приложении `InitInstance` находится в функции участника приложения.

Стиль окна по умолчанию, используемый в приложении MDI, представляет собой сочетание **WS_CHILD,** **WS_OVERLAPPEDWINDOW**и **FWS_ADDTOTITLE** стилей. Чтобы изменить атрибуты окна детских окон приложения MDI, переувичайте функцию `CMDIChildWnd` [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) в вашем классе, полученную из. Пример:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Этот код создает детские окна MDI без кнопки «Максимизация».

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Стили Windows](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Стили окна кадра](../mfc/frame-window-styles-cpp.md)

- [Стили окна](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>См. также раздел

[Стили окна фрейма](../mfc/frame-window-styles-cpp.md)
