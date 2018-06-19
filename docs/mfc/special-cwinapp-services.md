---
title: Специальные службы CWinApp | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81c3804ccc4f9e30e2d287102c408c98a77c6833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382935"
---
# <a name="special-cwinapp-services"></a>Специальные службы CWinApp
Помимо выполнения цикла обработки сообщений и давая возможность инициализировать приложение и очистки после него, [CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько служб.  
  
##  <a name="_core_shell_registration"></a> Регистрация оболочки  
 По умолчанию мастер приложений MFC позволяет пользователю открывать файлы данных, созданные в приложении двойным щелчком в проводнике или диспетчера файлов. Если приложение работает с интерфейсом MDI и укажите расширение файлов, созданных приложением, мастер приложений MFC добавляет вызовы [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes) и [EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)функции-члены [CWinApp](../mfc/reference/cwinapp-class.md) для `InitInstance` переопределения, которое записывает для вас.  
  
 `RegisterShellFileTypes` Регистрирует типов документов приложения с помощью проводника или диспетчера файлов. Функция добавляет записи регистрационную базу данных, поддерживающий Windows. Операции регистрации каждого типа документа, связывание расширения файла с типом файла, задать командную строку, чтобы открыть приложение и задания команды динамических данных exchange (DDE), откройте документ этого типа.  
  
 `EnableShellOpen` завершает процесс, что позволяет приложению получать команды DDE из проводника или диспетчера файлов для открытия файла, выбранного пользователем.  
  
 Эта поддержка Автоматическая регистрация в `CWinApp` устраняет необходимость отправки REG-файл вместе с приложением или для выполнения работы в специальной установки.  
  
 Требуется инициализация GDI + для вашего приложения (путем вызова [GdiplusStartup](https://msdn.microsoft.com/library/ms534077) в ваш [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) функции), необходимо отключить в фоновом потоке GDI +.  
  
 Это можно сделать, задав **SuppressBackgroundThread** членом [GdiplusStartupInput](https://msdn.microsoft.com/library/ms534067) структуру **TRUE**. При подавлении GDI + фоновый поток, **NotificationHook** и **NotificationUnhook** следует вызывать перед входа и выхода из цикла обработки сообщений приложения. Дополнительные сведения об этих вызовов см. в разделе [GdiplusStartupOutput](https://msdn.microsoft.com/library/ms534068). Таким образом, поместите вызов **GdiplusStartup** и функции-обработчики уведомления будут находиться в переопределение виртуальной функции [CWinApp::Run](../mfc/reference/cwinapp-class.md#run), как показано ниже:  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 Если не нужно отключать фонового потока GDI +, DDE команды могут преждевременно выполняться приложению до начала создания основного окна. DDE команд, выполненных в оболочке может быть преждевременно прервана, что приводит к появлению сообщений об ошибках.  
  
##  <a name="_core_file_manager_drag_and_drop"></a> Перетаскивание диспетчера файлов  
 Файлы можно перетаскивать из окна представления файла в диспетчере файла или File Explorer окно в приложении. Например, возможно Включите один или несколько файлов для переноса главное окно MDI-приложения, где приложение может получить имена файлов и откройте дочерних MDI-окон для этих файлов.  
  
 Чтобы включить файл перетаскивания в приложении, мастер приложений MFC записывает вызов [CWnd](../mfc/reference/cwnd-class.md) функции-члена [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles) для главного окна фрейма в вашей `InitInstance`. Если вы не хотите реализовать функцию и перетащите этот вызов можно удалить.  
  
> [!NOTE]
>  Вы также можете реализовать более общие возможности перетаскивания и вставки, перетаскивания данных между или внутри документов — с OLE. Сведения см. в статье [перетаскивания и Drop (OLE)](../mfc/drag-and-drop-ole.md).  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> Позволяет отслеживать их наиболее недавно использовавшиеся документы  
 Как пользователь открывает и закрывает файлы, объект приложения хранит информацию о четырех последних использовавшихся файлов. Имена файлов добавляются в меню «файл» и обновляется при их изменении. Платформа хранит эти имена файлов в реестре или в INI-файле, с тем же именем, что и проект и считывает их из файла, при запуске приложения. `InitInstance` Переопределения, мастер приложений MFC создает для включает вызов [CWinApp](../mfc/reference/cwinapp-class.md) функции-члена [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings), который загружает данные из реестра и INI-файле файл, включая наиболее недавно использовать имена файлов.  
  
 Эти записи сохраняются следующим образом:  
  
-   В Windows NT, Windows 2000 и более поздней версии, значение хранится в раздел реестра.  
  
-   В Windows 3.x значение хранится в WIN. INI-файл.  
  
-   В Windows 95 и более поздних версиях значение хранится в кэшированная версия WIN. INI-ФАЙЛЕ.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)