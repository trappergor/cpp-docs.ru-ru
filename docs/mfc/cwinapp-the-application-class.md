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
ms.openlocfilehash: 8518e21a9fa6bcf5ac640cff25b17c5028046b06
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447025"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: класс приложений

Главный класс приложения в MFC инкапсулирует инициализацию, выполнение и завершение приложения для операционной системы Windows. Приложение, построенное на платформе, должно иметь один и только один объект класса, производного от [CWinApp](../mfc/reference/cwinapp-class.md). Этот объект создан до создания окон.

`CWinApp` является производным от `CWinThread`, который представляет основной поток выполнения для приложения, который может иметь один или несколько потоков. В последних версиях MFC функции элементов `InitInstance`, **Run**, `ExitInstance`и `OnIdle` фактически находятся в классе `CWinThread`. Эти функции обсуждаются, как если бы они были `CWinApp` членами, так как обсуждение касается роли объекта в качестве объекта приложения, а не основного потока.

> [!NOTE]
>  Класс приложения представляет собой основной поток выполнения приложения. С помощью функций API Win32 можно также создавать вторичные потоки выполнения. Эти потоки могут использовать библиотеку MFC. Дополнительные сведения см. в разделе [многопоточность](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Как и любая программа для операционной системы Windows, приложение платформы имеет функцию `WinMain`. Однако в приложении платформы вы не пишете `WinMain`. Он предоставляется библиотекой классов и вызывается при запуске приложения. `WinMain` выполняет стандартные службы, такие как регистрация классов окон. Затем он вызывает функции членов объекта приложения для инициализации и запуска приложения. (Можно настроить `WinMain` путем переопределения функций-членов `CWinApp`, которые `WinMain` вызовы.)

Чтобы инициализировать приложение, `WinMain` вызывает `InitApplication` и `InitInstance` функции члена объекта приложения. Чтобы запустить цикл обработки сообщений приложения, `WinMain` вызывает функцию **запуска** члена. При завершении работы `WinMain` вызывает функцию члена `ExitInstance` объекта приложения.

> [!NOTE]
>  Имена, **выделенные жирным шрифтом** в этой документации, указывают на элементы, C++предоставляемые Библиотека Microsoft Foundation Class и визуального элемента. Имена, показанные в `monospaced` типе, указывают на создаваемые или переопределяемые элементы.

## <a name="see-also"></a>См. также раздел

[Общие разделы по MFC](../mfc/general-mfc-topics.md)<br/>
[CWinApp и мастер приложений MFC](../mfc/cwinapp-and-the-mfc-application-wizard.md)<br/>
[Переопределяемые функции-члены CWinApp](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Специальные службы CWinApp](../mfc/special-cwinapp-services.md)
