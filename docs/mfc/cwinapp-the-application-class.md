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
ms.openlocfilehash: e8327cf55606131d43201aa1f4f51526bcba147a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617070"
---
# <a name="cwinapp-the-application-class"></a>CWinApp: класс приложений

Главный класс приложения в MFC инкапсулирует инициализацию, выполнение и завершение приложения для операционной системы Windows. Приложение, построенное на платформе, должно иметь один и только один объект класса, производного от [CWinApp](reference/cwinapp-class.md). Этот объект создан до создания окон.

`CWinApp`является производным от класса `CWinThread` , который представляет основной поток выполнения приложения, который может иметь один или несколько потоков. В последних версиях MFC `InitInstance` функции, и **запуска**, `ExitInstance` и, фактически, `OnIdle` находятся в классе `CWinThread` . Эти функции обсуждаются, как если бы они были `CWinApp` членами, так как обсуждение касается роли объекта в качестве объекта приложения, а не основного потока.

> [!NOTE]
> Класс приложения представляет собой основной поток выполнения приложения. С помощью функций API Win32 можно также создавать вторичные потоки выполнения. Эти потоки могут использовать библиотеку MFC. Дополнительные сведения см. в разделе [многопоточность](../parallel/multithreading-support-for-older-code-visual-cpp.md).

Как и любая программа для операционной системы Windows, приложение платформы имеет `WinMain` функцию. Однако в приложении платформы вы не пишите `WinMain` . Он предоставляется библиотекой классов и вызывается при запуске приложения. `WinMain`выполняет стандартные службы, такие как регистрация классов окон. Затем он вызывает функции членов объекта приложения для инициализации и запуска приложения. (Можно настроить `WinMain` путем переопределения `CWinApp` функций-членов, `WinMain` вызывающих.)

Для инициализации приложения `WinMain` вызывает функции и для объекта приложения `InitApplication` `InitInstance` . Чтобы запустить цикл обработки сообщений приложения, `WinMain` вызывается функция **запуска** члена. При завершении `WinMain` работы вызывается `ExitInstance` функция члена объекта приложения.

> [!NOTE]
> Имена, **выделенные жирным шрифтом** в этой документации, указывают на элементы, предоставляемые библиотека Microsoft Foundation Class и Visual C++. Имена, показанные в `monospaced` типе, обозначают создаваемые или переопределяемые элементы.

## <a name="see-also"></a>См. также раздел

[Общие разделы по MFC](general-mfc-topics.md)<br/>
[CWinApp и мастер приложений MFC](cwinapp-and-the-mfc-application-wizard.md)<br/>
[Переопределяемые функции членов CWinApp](overridable-cwinapp-member-functions.md)<br/>
[Специальные службы CWinApp](special-cwinapp-services.md)
