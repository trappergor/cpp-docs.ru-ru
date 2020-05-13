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
ms.openlocfilehash: 1f5abcdab3eda1304879b122acc8072951a0e6c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363907"
---
# <a name="special-cwinapp-services"></a>Специальные службы CWinApp

Помимо запуска цикла сообщений и предоставления вам возможности инициализировать приложение и очистить после него, [CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько других услуг.

## <a name="shell-registration"></a><a name="_core_shell_registration"></a>Регистрация оболочки

По умолчанию Мастер приложений MFC позволяет пользователю открывать файлы данных, созданные вашим приложением, дважды нажав на них в File Explorer или File Manager. Если ваше приложение является приложением MDI, и вы указываете расширение для файлов, которые создает приложение, Волшебник приложения MFC добавляет `InitInstance` вызовы в [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) и [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen) функции членов [CWinApp](../mfc/reference/cwinapp-class.md) к переопределению, которое оно пишет для вас.

`RegisterShellFileTypes`регистрирует типы документов приложения с помощью File Explorer или File Manager. Функция добавляет записи в базу данных регистрации, которую поддерживает Windows. Записи регистрируют каждый тип документа, связывают расширение файла с типом файла, указывают командную строку для открытия приложения и указывают команду динамического обмена данными (DDE) для открытия документа такого типа.

`EnableShellOpen`завершает процесс, позволяя приложению получать команды DDE от File Explorer или File Manager, чтобы открыть выбранный пользователем файл.

Эта автоматическая `CWinApp` поддержка регистрации устраняет необходимость отправки файла .reg с вашим приложением или для специальных работ по установке.

Если вы хотите инициализировать GDI для вашего приложения (позвонив [в GdiplusStartup](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup) в функции [InitInstance),](../mfc/reference/cwinapp-class.md#initinstance) необходимо подавить фоновый поток GDI.

Вы можете сделать `SuppressBackgroundThread` это, установив член [структуры GdiplusStartupInput](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput) к **TRUE**. При подавлении фонового потока `NotificationHook` GDI должны `NotificationUnhook` совершаться звонки непосредственно перед входом и выходом из цикла сообщений приложения. Для получения дополнительной информации об этих вызовах, [см.](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput) Таким образом, хорошее `GdiplusStartup` место для вызова и функции уведомления крючка будет в переопределение виртуальной функции [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), как показано ниже:

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

Если вы не подавляете фоновый поток GDI, команды DDE могут быть преждевременно выданы приложению до создания его основного окна. Команды DDE, выданные оболочкой, могут быть досрочно прерваны, что приведет к сообщениям об ошибках.

## <a name="file-manager-drag-and-drop"></a><a name="_core_file_manager_drag_and_drop"></a>Менеджер файлов Перетащите и падение

Файлы могут быть перетащены из окна представления файла в файле Manager или File Explorer в окно в приложении. Например, можно включить один или несколько файлов, которые будут перетащить в основное окно приложения MDI, где приложение может получить имена файлов и открыть окна для файлов MDI.

Для включения в приложение перетаскивания файлов Волшебник приложения MFC записывает вызов в функцию участника [CWnd](../mfc/reference/cwnd-class.md) [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) для вашего окна основного кадра в вашем. `InitInstance` Вы можете удалить этот вызов, если вы не хотите реализовать функцию перетаскивания.

> [!NOTE]
> Можно также реализовать более общие возможности перетаскивания — перетаскивание данных между документами или внутри них – с OLE. Для получения информации, см. статью [OLE перетащить и падение](../mfc/drag-and-drop-ole.md).

## <a name="keeping-track-of-the-most-recently-used-documents"></a><a name="_core_keeping_track_of_the_most_recently_used_documents"></a>Отслеживание последних используемых документов

Когда пользователь открывает и закрывает файлы, объект приложения отслеживает четыре последних использованных файла. Имена этих файлов добавляются в меню файла и обновляются при изменении. Рамки хранят эти имена файлов в реестре или в файле .ini, с тем же именем, что и ваш проект, и читает их из файла при запуске приложения. Переопределение `InitInstance`, создаваемое мастером приложений MFC, включает вызов функции-члена [CWinApp](../mfc/reference/cwinapp-class.md)[LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), который загружает сведения из реестра или INI-файла, включая последний использовавшийся файл Фамили.

Эти записи хранятся следующим образом:

- В Windows NT, Windows 2000, а затем значение хранится в ключе реестра.

- В Windows 3.x значение хранится в WIN. Файл INI.

- В Windows 95 и позже значение хранится в кэшированной версии WIN. Ini.

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
