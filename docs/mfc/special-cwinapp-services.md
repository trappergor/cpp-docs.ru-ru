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
ms.openlocfilehash: 8dd69538cc322fe8518a33444b71171a936a02aa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487533"
---
# <a name="special-cwinapp-services"></a>Специальные службы CWinApp

Помимо выполнения цикла обработки сообщений и давая возможность для инициализации этого приложения и очистки после него, [CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько служб.

##  <a name="_core_shell_registration"></a> Регистрация оболочки

По умолчанию мастер приложений MFC позволяет пользователю открыть файлы данных, созданные в приложении двойным щелчком в проводнике или диспетчера файлов. Если приложение является MDI-приложения и укажите расширение файлов, созданных приложением, мастер приложений MFC добавляет вызовы [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) и [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)функции-члены [CWinApp](../mfc/reference/cwinapp-class.md) для `InitInstance` переопределение, которое осуществляется запись для вас.

`RegisterShellFileTypes` Регистрирует типов документов приложения с помощью проводника или диспетчера файлов. Функция добавляет записи в базу данных регистрации, который поддерживает Windows. Операции регистрации каждого типа документа, сопоставление расширения файла с типом файла, указать командную строку, чтобы открыть приложение и укажите команду exchange (DDE) платформы динамических данных для открытия документа этого типа.

`EnableShellOpen` завершает процесс, позволяя приложению для получения команд DDE из проводника или диспетчер файлов для открытия файла, выбранного пользователем.

Эта поддержка автоматической регистрации в `CWinApp` избавляет от необходимости отправки REG-файла с приложением или для выполнения работы специальной установки.

Если вы хотите инициализировать GDI + для вашего приложения (путем вызова [GdiplusStartup](/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) в вашей [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) функции), необходимо отключить фоновый поток GDI +.

Это можно сделать, задав `SuppressBackgroundThread` членом [GdiplusStartupInput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) структуру **TRUE**. При подавлении GDI + фоновый поток, `NotificationHook` и `NotificationUnhook` следует вызывать перед входа и выхода из цикла обработки сообщений приложения. Дополнительные сведения об этих вызовов, см. в разделе [GdiplusStartupOutput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput). Таким образом, лучше всего вызывать `GdiplusStartup` и функции-обработчики уведомлений будут находиться в переопределение виртуальной функции [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), как показано ниже:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Если не следует отключать фоновый поток GDI +, DDE команды могут преждевременно выполняться в приложение до начала создания основного окна. DDE команды оболочки может быть преждевременно прервана, приводит к сообщения об ошибках.

##  <a name="_core_file_manager_drag_and_drop"></a> Перетаскивание диспетчера файлов

Файлы можно перетаскивать из окна представления файла в диспетчер файлов или File Explorer в окно в приложении. Пользователь может например, включить один или несколько файлов, которые можно перетаскивать в главное окно MDI-приложения, где приложение может получить имена файлов и откройте дочерние MDI-окна для этих файлов.

Чтобы включить файл перетаскивания в приложении, мастер приложений MFC записывает вызов [CWnd](../mfc/reference/cwnd-class.md) функция-член [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) для вашего окна главного фрейма в вашей `InitInstance`. Этот вызов можно удалить, если вы не хотите реализовать функцию перетаскивания и вставки.

> [!NOTE]
>  Вы также можете реализовать более общие возможности перетаскивания и вставки — перетаскивание данных между или внутри документов — с OLE. Сведения см. в статье [Drag and Drop (OLE)](../mfc/drag-and-drop-ole.md).

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Слежении за наиболее недавно использовавшиеся документы

Пользователь открывает и закрывает файлы, объект приложения следит за четыре самых последних использовавшихся файлов. Имена этих файлов добавляются в меню "файл" и обновляется, когда их изменения. Платформа хранит имена файлов в реестре или в INI-файле, с тем же именем, что и проект и считывает их из файла, при запуске приложения. `InitInstance` Переопределения, что мастер приложений MFC создает для включает вызов [CWinApp](../mfc/reference/cwinapp-class.md) функция-член [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), который загружает данные из реестра и INI-файле файл, включая наиболее недавно используемые имена файлов.

Эти записи сохраняются следующим образом:

- В Windows NT, Windows 2000 и более поздней версии, значение хранится в раздел реестра.

- В Windows 3.x, значение сохраняется в WIN. INI-файл.

- В Windows 95 и более поздних версиях значение хранится в кэшированной версии WIN. INI.

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)