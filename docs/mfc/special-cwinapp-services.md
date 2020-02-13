---
title: Специальные службы CWinApp
ms.date: 11/04/2016
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
ms.openlocfilehash: 04c7357d67dc1a5daee4b8b8135c9a54eda8504a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127833"
---
# <a name="special-cwinapp-services"></a>Специальные службы CWinApp

Помимо выполнения цикла обработки сообщений и предоставления возможности инициализировать приложение и выполнить очистку после него, [CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько других служб.

##  <a name="_core_shell_registration"></a>Регистрация оболочки

По умолчанию мастер приложений MFC предоставляет пользователю возможность открывать файлы данных, созданные приложением, дважды щелкнув их в проводнике или в диспетчере файлов. Если приложение является приложением MDI и вы указали расширение для файлов, создаваемых приложением, мастер приложений MFC добавляет вызовы функций-членов [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) и [енаблешеллопен](../mfc/reference/cwinapp-class.md#enableshellopen) класса [CWinApp](../mfc/reference/cwinapp-class.md) в переопределение `InitInstance`, которое он записывает.

`RegisterShellFileTypes` регистрирует типы документов приложения в проводнике или с помощью диспетчера файлов. Функция добавляет записи в базу данных регистрации, которую поддерживает Windows. Записи регистрируют каждый тип документа, связывают расширение файла с типом файла, указывают командную строку для открытия приложения и задают команду динамического обмена данными (DDE), чтобы открыть документ этого типа.

`EnableShellOpen` завершает процесс, позволяя приложению получить команды DDE из проводника или диспетчера файлов, чтобы открыть файл, выбранный пользователем.

Эта поддержка автоматической регистрации в `CWinApp` устраняет необходимость в поставке REG-файла с приложением или специальной работы по установке.

Если требуется инициализировать GDI+ для приложения (путем вызова [гдиплусстартуп](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) в функции [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) ), необходимо подавить фоновый поток GDI+.

Это можно сделать, задав для элемента `SuppressBackgroundThread` структуры [Гдиплусстартупинпут](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) **значение true**. При подавлении фонового потока GDI+ вызовы `NotificationHook` и `NotificationUnhook` должны быть сделаны непосредственно перед вводом и выходом из цикла обработки сообщений приложения. Дополнительные сведения об этих вызовах см. в разделе [гдиплусстартупаутпут](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput). Таким образом, хорошим местом вызова `GdiplusStartup` и функций уведомления о обработчиках будет переопределена виртуальная функция [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run), как показано ниже:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Если не отключить фоновый поток GDI+, команды DDE могут быть преждевременно выданы приложению до создания главного окна. Команды DDE, выданные оболочкой, могут преждевременно прерываться, в результате чего выдаются сообщения об ошибках.

##  <a name="_core_file_manager_drag_and_drop"></a>Перетаскивание диспетчера файлов

Файлы можно перетаскивать из окна просмотра файлов в диспетчере файлов или проводника в окно приложения. Например, можно включить один или несколько файлов для перетаскивания в главное окно приложения MDI, где приложение может извлечь имена файлов и открыть дочерние окна MDI для этих файлов.

Чтобы включить перетаскивание файлов в приложение, мастер приложений MFC записывает вызов функции-члена [CWnd](../mfc/reference/cwnd-class.md) [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) для основного окна фрейма в `InitInstance`. Вы можете удалить этот вызов, если не хотите реализовывать функцию перетаскивания.

> [!NOTE]
>  Можно также реализовать более общие возможности перетаскивания — перетаскивание данных между или внутри документов с помощью OLE. Дополнительные сведения см. в статье [перетаскивание OLE](../mfc/drag-and-drop-ole.md).

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a>Отслеживание недавно использовавшихся документов

Когда пользователь открывает и закрывает файлы, объект приложения отслеживает четыре последних использованных файла. Имена этих файлов добавляются в меню файл и обновляются при их изменении. Платформа хранит эти имена файлов либо в реестре, либо в ini-файле с тем же именем, что и у проекта, и считывает их из файла при запуске приложения. Переопределение `InitInstance`, создаваемое мастером приложений MFC, включает вызов функции-члена [CWinApp](../mfc/reference/cwinapp-class.md)[LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), который загружает сведения из реестра или INI-файла, включая последний использовавшийся файл Фамили.

Эти записи хранятся следующим образом:

- В Windows NT, Windows 2000 и более поздних версиях значение хранится в разделе реестра.

- В Windows 3. x значение сохраняется в ВЫИГРЫШе. INI-файл.

- В Windows 95 и более поздних версиях значение сохраняется в кэшированной версии WIN. Ссылки.

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
