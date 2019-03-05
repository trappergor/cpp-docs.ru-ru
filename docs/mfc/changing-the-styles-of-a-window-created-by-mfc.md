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
ms.openlocfilehash: c8a3a5d9b8b007887dfb31f7459c0269377b38fd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294165"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>Изменение стилей окна, созданного MFC

В свою версию `WinMain` функции MFC регистрирует несколько классов стандартное окно для вас. Так как MFC обычно не изменяйте `WinMain`, что позволяет предусмотрена возможность изменить стили окна по умолчанию MFC. В этой статье объясняется, как изменить стили такого класса предварительно окно в существующем приложении.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Изменение стилей в новое приложение MFC

Если вы используете Visual C++ 2.0 или более поздней версии, можно изменить стили окна по умолчанию в мастере приложений при создании приложения. На странице функций интерфейса пользователя в мастере приложений можно изменить стили для фрейма главного окна и дочерние окна MDI. Для любого типа окна, можно указать ее толщину рамки ("толстые" или "тонких") и любой из следующих:

- Имеет ли окно свернуть или развернуть элементы управления.

- Окна, появится ли изначально свернутое в развернутом состоянии, или ни одного.

Для главного фрейма windows можно также указать, имеет ли окно системное меню. Для дочерних окон интерфейса MDI можно указать, поддерживает ли окно области разделителя.

##  <a name="_core_changing_styles_in_an_existing_application"></a> Изменение стилей в существующее приложение

При изменении атрибутов окна в существующем приложении, выполните инструкции в оставшейся части этой статьи.

Чтобы изменить атрибуты окна по умолчанию, используемый приложением framework, созданных с помощью мастера приложений, переопределите окна [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) виртуальная функция-член. `PreCreateWindow` позволяет приложению получить доступ к процесс создания, обычно управляется внутренне [CDocTemplate](../mfc/reference/cdoctemplate-class.md) класса. Платформа вызывает `PreCreateWindow` непосредственно перед Создание окна. Изменив [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa) структуры передается `PreCreateWindow`, приложение может изменить атрибуты, используемые для создания окна. Например чтобы убедиться, что окно не использует заголовок, используйте следующие побитовой операции:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../visual-cpp-samples.md) пример приложения демонстрирует этот метод для изменение атрибутов окна. В зависимости от изменений в приложении `PreCreateWindow`, может потребоваться Вызовите реализацию базового класса функции.

Ниже представлено описание SDI так и [случай MDI](#_core_the_mdi_case).

##  <a name="_core_the_sdi_case"></a> В случае SDI

В приложении с интерфейсом (SDI) одного документа, стиль окна по умолчанию в framework представляет собой сочетание **WS_OVERLAPPEDWINDOW** и **FWS_ADDTOTITLE** стили. **FWS_ADDTOTITLE** является стиле конкретного MFC, который указывает, что добавляемая платформа заголовок документа для заголовка окна. Чтобы изменить атрибуты окна в приложении SDI, переопределите `PreCreateWindow` функции в класс производным от `CFrameWnd` (который имена мастера приложений `CMainFrame`). Пример:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Этот код создает главное окно без кнопки свертывания и развертывания и масштабируемые границы. Окно изначально является по центру экрана.

##  <a name="_core_the_mdi_case"></a> В случае MDI

Чтобы изменить стиль окна дочернего окна в приложении несколько интерфейса (MDI) документа требуется немного больше работы. По умолчанию, созданных с помощью мастера приложений MDI-приложения использует значение по умолчанию [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) класс, определенный в MFC. Чтобы изменить стиль окна дочернего окна интерфейса MDI, должен быть производным от нового класса `CMDIChildWnd` и замените все ссылки на `CMDIChildWnd` в проекте со ссылками на новый класс. Скорее всего, только ссылка на `CMDIChildWnd` в приложение находится в вашем приложении `InitInstance` функция-член.

Стиль окна по умолчанию, используемые в приложениях MDI представляет собой сочетание **WS_CHILD**, **WS_OVERLAPPEDWINDOW**, и **FWS_ADDTOTITLE** стили. Чтобы изменить атрибуты окна дочерних окон MDI-приложения, переопределите [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) функции в класс производным от `CMDIChildWnd`. Пример:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Этот код создает дочерней MDI-формы windows без кнопки развертывания.

### <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Стили Windows](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Стили окна фрейма](../mfc/frame-window-styles-cpp.md)

- [Стили окна](/windows/desktop/winmsg/window-styles)

## <a name="see-also"></a>См. также

[Стили окна фрейма](../mfc/frame-window-styles-cpp.md)
