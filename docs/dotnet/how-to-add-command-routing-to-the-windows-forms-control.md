---
title: Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: ad64a12051c22a0cfca99d3ec9c5abef579902f4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365174"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms

[CWinFormsView](../mfc/reference/cwinformsview-class.md) направляет команды и сообщения пользовательского интерфейса с обновлением-командой, чтобы позволить ему обрабатывать команды MFC (например, элементы меню кадра и кнопки панели инструментов).

Пользовательский контроль использует [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) для хранения ссылки `m_CmdSrc`на объект исходного кода команды в, как показано в следующем примере. Для `ICommandTarget` использования необходимо добавить ссылку на mfcmifc80.dll.

`CWinFormsView`обрабатывает несколько общих уведомлений о представлении MFC, перенаправляя их в управляемый пользовательский контроль. Эти уведомления включают методы [OnInitialUpdate,](../mfc/reference/iview-interface.md#oninitialupdate) [OnUpdate](../mfc/reference/iview-interface.md#onupdate) и [OnActivateView.](../mfc/reference/iview-interface.md#onactivateview)

Эта тема предполагает, что вы ранее завершили [Как: Создать управление пользователем и хостом в поле Dialog](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создать пользовательский контроль и хост MDI View.](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

### <a name="to-create-the-mfc-host-application"></a>Создание приложения мСТ

1. Открыть библиотеку управления формами Windows, созданную в журнале [How to: Создание управления пользователями и хостов в dialog Box.](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

1. Добавьте ссылку на mfcmifc80.dll, которую вы можете сделать, нажав правой кнопкой наклять узла проекта в **Solution Explorer,** выбрав **Добавить,** **Справка**, а затем просмотр в Microsoft Visual Studio 10.0 "VC'atlmfc'lib.

1. Откройте UserControl1.Designer.cs и добавьте следующее с помощью оператора:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Кроме того, в UserControl1.Designer.cs, изменить эту строку:

    ```
    partial class UserControl1
    ```

   на такой:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Добавьте это в качестве первой `UserControl1`строки определения класса для:

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Добавьте следующие определения `UserControl1` метода (мы создадим идентификатор управления MFC на следующем этапе):

    ```
    public void Initialize (ICommandSource cmdSrc)
    {
       m_CmdSrc = cmdSrc;
       // need ID of control in MFC dialog and callback function
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));
    }

    private void singleMenuHandler (uint cmdUI)
    {
       // User command handler code
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");
    }
    ```

1. Откройте приложение MFC, созданное в [«Как: создать пользовательский контроль и host MDI View».](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

1. Добавьте опцию меню, `singleMenuHandler`которая будет вызывать.

   Перейдите в **представление ресурсов** (Ctrl-Shift-E), расширьте папку **меню,** а затем дважды щелкните **IDR_MFC02TYPE**. Это отображает редактор меню.

   Добавьте опцию меню в нижней части меню **View.** Обратите внимание на идентификатор опции меню в окне **Свойства.** Сохраните файл.

   В **Solution Explorer**откройте файл Resource.h, скопируйте значение идентификатора для только что `m_CmdSrc.AddCommandHandler` добавленного опции меню `Initialize` и вставьте это значение в качестве первого параметра для вызова в методе проекта C '(при необходимости замены). `32771`

1. Постройте и запустите проект.

   В меню **Сборка** выберите **Построить решение**.

   В меню **Debug** нажмите **«Старт» без отладки.**

   Выберите добавленный вариант меню. Обратите внимание, что метод в .dll вызывается.

## <a name="see-also"></a>См. также раздел

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)<br/>
[Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)
