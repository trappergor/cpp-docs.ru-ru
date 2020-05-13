---
title: 'CWinApp: класс приложений'
ms.date: 11/04/2016
helpviewer_keywords:
- application class [MFC]
- CWinApp class [MFC], CWinThread
- MFC, WinMain and
- CWinApp class [MFC], multithreading
- CWinThread class [MFC], and CWinApp
- InitApplication method [MFC]
- WinMain method [MFC]
- WinMain method [MFC], in MFC
- CWinApp class [MFC], WinMain
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
ms.openlocfilehash: 007a4e53fd9b3eae612947cd76ee352776572d4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373526"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: класс приложений

Основной класс приложений в MFC инкапсулирует инициализацию, запуск и прекращение приложения для операционной системы Windows. Приложение, построенное на фреймворке, должно иметь один и только один объект класса, полученный из [CWinApp.](../mfc/reference/cwinapp-class.md) Этот объект построен до создания окон.

`CWinApp`происходит от `CWinThread`, который представляет собой основную нить выполнения для вашего приложения, который может иметь один или несколько потоков. В последних версиях `InitInstance`MFC, `ExitInstance`, `OnIdle` **Run**, и `CWinThread`функции члена на самом деле в классе. Эти функции обсуждаются здесь, как если бы они были `CWinApp` членами, а не, потому что обсуждение касается роли объекта как объекта приложения, а не как основной поток.

> [!NOTE]
> Класс приложения является основной нити выполнения приложения. Используя функции API Win32, можно также создавать вторичные потоки выполнения. Эти потоки можно использовать в библиотеке MFC. Для получения дополнительной [информации см.](../parallel/multithreading-support-for-older-code-visual-cpp.md)

Как и любая программа для операционной `WinMain` системы Windows, ваше фреймворкное приложение имеет функцию. В рамочном приложении, однако, вы не пишете. `WinMain` Он поставляется библиотекой класса и вызывается при запуске приложения. `WinMain`выполняет стандартные услуги, такие как регистрация классов окон. Затем он вызывает функции участника объекта приложения для инициализации и запуска приложения. (Вы можете `WinMain` настроить, переопределив функции `CWinApp` участника, которые `WinMain` вызывает.)

Чтобы инициализировать приложение, `WinMain` вызывает `InitApplication` `InitInstance` функции объекта приложения и членов. Чтобы запустить цикл сообщения приложения, `WinMain` вызывает функцию участника **Run.** При прекращении `WinMain` вызывает функцию `ExitInstance` члена объекта приложения.

> [!NOTE]
> Имена, указанные **жирным шрифтом** в этой документации, указывают на элементы, поставляемые библиотекой класса Microsoft Foundation и Visual C. Имена, `monospaced` отображаемые в типе, указывают элементы, которые вы создаете или переопределить.

## <a name="see-also"></a>См. также раздел

[Общие темы МФЦ](../mfc/general-mfc-topics.md)<br/>
[CWinApp и мастер приложений MFC](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Переизбытые функции членов CWinApp](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Специальные службы CWinApp](../mfc/special-cwinapp-services.md)
