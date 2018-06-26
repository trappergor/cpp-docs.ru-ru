---
title: Предоставление активации без окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a42d952ade479c4eb117d21921c9b0feafb81cea
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931955"
---
# <a name="providing-windowless-activation"></a>Предоставление активации без окна
Окно создания кода (то есть все, что происходит при вызове `CreateWindow`) является дорогостоящим для выполнения. Элемент управления, который поддерживает на экране окна должна управлять сообщения окна. Элементы управления без окон, следовательно, быстрее, чем элементы управления в windows.  
  
 Дальнейшие преимуществами элементов управления без окон том, что, в отличие от элементов управления с окнами, поддерживающих элементы управления поддерживают прозрачный Рисование и области непрямоугольного экрана. Распространенным примером прозрачный элемент управления является элементом управления текст с прозрачным фоном. Элементы управления рисует текст, но не фоновом режиме, поэтому все, что находится ниже текст отображается через. Новой формы сделать часто используют непрямоугольных элементов управления, например кнопки со стрелками и округления кнопок.  
  
 Часто, элемент управления не требуется для окна и, вместо этого можно использовать для служб Windows для своего контейнера, при условии, что контейнер записан в поддерживающих объекты. Обратно совместимы с более старых контейнеры элементов управления без окон. В более старых контейнеры не написано для поддержки элементов управления без окон элементов управления без окон создать окно активном состоянии.  
  
 Так как элементы управления без окон не имеют свои собственные окна, контейнера (которая имеет окна) отвечает за предоставление служб, которые бы в противном случае были предоставлены с помощью элемента управления собственного окна. Например если элемент управления должен запросить фокус клавиатуры, захватывающий мышь или получить контекст устройства, эти операции управляются контейнером. Контейнер направляет пользователя входного сообщения, отправленные его окна, чтобы соответствующий элемент управления без окон, с помощью `IOleInPlaceObjectWindowless` интерфейса. (См. *ActiveX SDK* описание этого интерфейса.) `COleControl` эти службы из контейнера вызова функций-членов.  
  
 Чтобы использовать активации без окна элемента управления, включают **windowlessActivate** флаг в набор флагов, возвращенных [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]  
  
 Код, чтобы включить этот флаг создается автоматически при выборе **активации без окна** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страница мастера элементов управления ActiveX MFC.  
  
 При включении активации без окна контейнера будут делегировать входящих сообщений для элемента управления `IOleInPlaceObjectWindowless` интерфейса. `COleControl`в реализации этого интерфейса отправляет сообщения через схему сообщений для элемента управления, после настройки мыши координирует соответствующим образом. Сообщения, как и обычные окна сообщения, можно обрабатывать, добавив соответствующие записи в схеме сообщений. В вашей обработчики для этих сообщений, избегайте использования *m_hWnd* переменную-член (или любую функцию-член, которые его используют) без проверки, его значение не **NULL**.  
  
 `COleControl` предоставляет функции-члены, вызывающие захват мыши, фокуса клавиатуры, прокрутка и другие окна службы из контейнера соответствующим образом, включая:  
  
-   [При получении фокуса](../mfc/reference/colecontrol-class.md#getfocus), [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)  
  
-   [GetCapture](../mfc/reference/colecontrol-class.md#getcapture), [SetCapture](../mfc/reference/colecontrol-class.md#setcapture), [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)  
  
-   [GetDC](../mfc/reference/colecontrol-class.md#getdc), [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)  
  
-   [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)  
  
-   [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)  
  
-   [Метода GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)  
  
 Без окон элементов управления, следует всегда использовать `COleControl` вместо соответствующих функций-членов `CWnd` функций-членов и их связанные функции Win32 API.  
  
 Вы можете быть целевым объектом операции перетаскивания и вставки OLE без окна элемента управления. Как правило это потребует, окна элемента управления быть зарегистрированы в качестве цели перетаскивания. Так как элемент управления не имеет окна свои собственные, в контейнере используется отдельное окно местом назначения. Элемент управления предоставляет реализацию `IDropTarget` интерфейс, к которому контейнера можно делегат вызывает в соответствующее время. Чтобы предоставить этот интерфейс к контейнеру, переопределите [COleControl::GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget). Пример:  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

