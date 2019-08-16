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
ms.openlocfilehash: ef79fc88604d565a942fdb0ae07d5fc5a2e0ebeb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509010"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Изменение стилей окна, созданного MFC

В своей версии `WinMain` функции MFC регистрирует несколько стандартных классов окон. Так как обычно не редактируется MFC `WinMain`, эта функция не позволяет изменять стили окон по умолчанию для MFC. В этой статье объясняется, как можно изменить стили такого класса с предварительно зарегистрированным окном в существующем приложении.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>Изменение стилей в новом приложении MFC

Если вы используете Visual C++ 2,0 или более поздней версии, вы можете изменить стили окна по умолчанию в мастере приложений при создании приложения. На странице функций пользовательского интерфейса мастера приложений можно изменить стили для основного окна фрейма и дочерних окон MDI. Для любого типа окна можно указать толщину фрейма (толстую или тонкую) и любой из следующих элементов:

- Содержит ли окно элементы управления "Minimize" или "развернуто".

- Отображается ли окно изначально в режиме сворачивания, развернуто или ни на один.

В окнах главного фрейма можно также указать, имеется ли в окне Системное меню. Для дочерних окон MDI можно указать, поддерживает ли окно панели разделения.

##  <a name="_core_changing_styles_in_an_existing_application"></a>Изменение стилей в существующем приложении

Если вы изменяете атрибуты окна в существующем приложении, следуйте инструкциям, приведенным в оставшейся части этой статьи.

Чтобы изменить атрибуты окна по умолчанию, используемые приложением платформы, созданным с помощью мастера приложений, переопределите виртуальную функцию-член [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) окна. `PreCreateWindow`позволяет приложению получить доступ к процессу создания, обычно управляемому классом [CDocTemplate](../mfc/reference/cdoctemplate-class.md) . Платформа вызывает `PreCreateWindow` непосредственно перед созданием окна. Изменяя структуру [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) , переданную в `PreCreateWindow`, приложение может изменять атрибуты, используемые для создания окна. Например, чтобы убедиться, что в окне не используется заголовок, используйте следующую побитовую операцию:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

Пример приложения [CTRLBARS](../overview/visual-cpp-samples.md) демонстрирует этот метод для изменения атрибутов окна. В зависимости от того, что приложение изменяет `PreCreateWindow`в, может потребоваться вызов реализации функции в базовом классе.

В следующем обсуждении рассматривается вариант использования SDI и [MDI](#_core_the_mdi_case).

##  <a name="_core_the_sdi_case"></a>Вариант SDI

В приложении с одним документом (SDI) стиль окна по умолчанию в платформе является сочетанием стилей **WS_OVERLAPPEDWINDOW** и **FWS_ADDTOTITLE** . **FWS_ADDTOTITLE** — это характерный для MFC стиль, который указывает платформе добавить заголовок документа в заголовок окна. Чтобы изменить атрибуты окна в приложении SDI, переопределите `PreCreateWindow` функцию в классе, производную от `CFrameWnd` (имя `CMainFrame`мастера приложений). Например:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Этот код создает главное окно фрейма без кнопок сворачивания и развертывания и без изменяемой границы. Изначально окно располагается по центру экрана.

##  <a name="_core_the_mdi_case"></a>Вариант MDI

Для изменения стиля окна дочернего окна в приложении многодокументного интерфейса (MDI) требуется немного больше работы. По умолчанию приложение MDI, созданное с помощью мастера приложений, использует класс [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) по умолчанию, определенный в MFC. Чтобы изменить стиль окна дочернего окна MDI, необходимо создать новый класс из `CMDIChildWnd` и заменить все ссылки на `CMDIChildWnd` в проекте ссылками на новый класс. Скорее всего, единственная ссылка на `CMDIChildWnd` приложение находится в функции- `InitInstance` члене приложения.

Стиль окна по умолчанию, используемый в приложении MDI, представляет собой сочетание стилей **WS_CHILD**, **WS_OVERLAPPEDWINDOW**и **FWS_ADDTOTITLE** . Чтобы изменить атрибуты окна дочерних окон приложения MDI, переопределите функцию [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) в классе, производном от `CMDIChildWnd`. Например:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Этот код создает дочерние MDI-окна без кнопки развертывания.

### <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Стили Windows](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

- [Стили окна](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>См. также

[Стили окна фрейма](../mfc/frame-window-styles-cpp.md)
