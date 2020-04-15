---
title: Практическое руководство. Добавление поддержки диспетчера перезапуска
ms.date: 11/04/2016
helpviewer_keywords:
- Restart manager [MFC]
- C++, application crash support
ms.assetid: 7f3f5867-d4bc-4ba8-b3c9-dc1e7be93642
ms.openlocfilehash: 7cf3fede663a7c4bc85573e17dd9c2f8bf3622b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373318"
---
# <a name="how-to-add-restart-manager-support"></a>Практическое руководство. Добавление поддержки диспетчера перезапуска

Менеджер перезагрузки — это функция, добавленная в Visual Studio для Windows Vista или более поздних операционных систем. Диспетчер перезапуска обеспечивает функции поддержки для приложения в случае его непредвиденного закрытия или перезапуска. Поведение диспетчера перезапуска зависит от типа приложения. Если приложение является редактором документов, то диспетчер перезапуска позволяет приложению автоматически сохранять состояние и содержимое всех открытых документов, а затем перезапускает приложение после непредвиденного закрытия. Если приложение не является редактором документов, диспетчер перезапуска перезапускает приложение, однако не может сохранить состояние приложения по умолчанию.

После перезапуска приложение выводит диалоговое окно задач (для Юникода). Если это приложение ANSI, оно выводит окно сообщения Windows. На этом этапе пользователь выбирает, нужно ли восстановить автоматически сохраненные документы. Если пользователь не восстанавливает автоматически сохраненные документы, диспетчер перезапуска удаляет временные файлы.

> [!NOTE]
> Поведение диспетчера перезапуска по умолчанию можно переопределить для сохранения данных и перезапуска приложения.

По умолчанию приложения MFC, созданные с помощью мастера проекта в Visual Studio, поддерживают менеджер перезагрузки, когда приложения запускаются на компьютере с Windows Vista или более поздней операционной системой. Если поддержка диспетчера перезапуска в приложении не требуется, можно отключить диспетчер перезапуска в мастере создания проекта.

### <a name="to-add-support-for-the-restart-manager-to-an-existing-application"></a>Добавление поддержки диспетчера перезапуска в существующее приложение

1. Откройте существующее приложение MFC в Visual Studio.

1. Откройте исходный файл для основного приложения. По умолчанию это CPP-файл, который имеет то же имя, что и приложение. Например, исходный файл основного приложения для MyProject — MyProject.cpp.

1. Найдите конструктор для основного приложения. Например, если проект — MyProject, конструктор имеет имя `CMyProjectApp::CMyProjectApp()`.

1. Добавьте следующий код в конструктор.

```
    m_dwRestartManagerSupportFlags = AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS;
```

1. Убедитесь, что метод `InitInstance` приложения вызывает родительский метод `InitInstance` : [CWinApp::InitInstance](../mfc/reference/cwinapp-class.md#initinstance) или `CWinAppEx::InitInstance`. Метод `InitInstance` отвечает за проверку *m_dwRestartManagerSupportFlags* параметров.

1. Скомпилируйте и запустите приложение.

## <a name="see-also"></a>См. также раздел

[Класс CDataRecoveryHandler](../mfc/reference/cdatarecoveryhandler-class.md)<br/>
[CWinApp::m_dwRestartManagerSupportFlags](../mfc/reference/cwinapp-class.md#m_dwrestartmanagersupportflags)<br/>
[Класс CWinApp](../mfc/reference/cwinapp-class.md)<br/>
[CWinApp::m_nAutosaveInterval](../mfc/reference/cwinapp-class.md#m_nautosaveinterval)<br/>
[Документ::OnDocumentEvent](../mfc/reference/cdocument-class.md#ondocumentevent)
