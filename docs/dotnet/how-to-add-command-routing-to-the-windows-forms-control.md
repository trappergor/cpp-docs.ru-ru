---
title: Практическое руководство. Добавление команды управления маршрутизации для Windows Forms
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
ms.openlocfilehash: 8f633cf744314833409a3ffeacf8c850429e099c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222914"
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Практическое руководство. Добавление команды управления маршрутизации для Windows Forms

[CWinFormsView](../mfc/reference/cwinformsview-class.md) направляет команды и сообщения пользовательского интерфейса команды update в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов).

Пользовательский элемент управления использует [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) для хранения ссылки на объект источника команды в `m_CmdSrc`, как показано в следующем примере. Чтобы использовать `ICommandTarget` необходимо добавить ссылку на библиотеку mfcmifc80.dll.

`CWinFormsView` обрабатывает несколько общих уведомлений MFC, перенаправляя их в управляемый пользовательский элемент управления. Эти уведомления входят [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) и [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) методы.

В этом разделе предполагается, вы выполнили ранее [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создание пользовательского элемента управления и узла Просмотр MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC

1. Откройте Библиотека элементов управления Windows Forms, которые вы создали в [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).

1. Добавьте ссылку на библиотеку mfcmifc80.dll, можно сделать, щелкнув правой кнопкой мыши узел проекта в **обозревателе решений**, выбрав **добавить**, **ссылку**и затем перейдите в Microsoft Visual Studio 10.0\VC\atlmfc\lib.

1. Откройте файл UserControl1.Designer.cs и добавьте следующий оператор using:

    ```
    using Microsoft.VisualC.MFC;
    ```

1. Кроме того в файле UserControl1.Designer.cs измените следующую строку:

    ```
    partial class UserControl1
    ```

   На эту:

    ```
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget
    ```

1. Добавить в качестве первой строки в определении класса для `UserControl1`:

    ```
    private ICommandSource m_CmdSrc;
    ```

1. Добавьте следующие определения метода в `UserControl1` (на следующем шаге создается идентификатор элемента управления MFC):

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

1. Откройте приложение MFC, созданное в [как: Создание пользовательского элемента управления и узла Просмотр MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).

1. Добавьте пункт меню, которое вызовет `singleMenuHandler`.

   Перейдите к **представление ресурсов** (Ctrl + Shift + E), разверните **меню** папку и дважды щелкните **IDR_MFC02TYPE**. Откроется редактор меню.

   Добавьте пункт меню в нижней части **представление** меню. Запишите или запомните идентификатор пункта меню в **свойства** окна. Сохраните файл.

   В **обозревателе решений**, откройте файл Resource.h, скопируйте значение идентификатора для добавленного пункта меню и вставьте это значение в качестве первого параметра для `m_CmdSrc.AddCommandHandler` вызова в проекте C# `Initialize` метод (заменив `32771` при необходимости).

9. Постройте и запустите проект.

   В меню **Сборка** выберите **Собрать решение**.

   На **Отладка** меню, щелкните **Запуск без отладки**.

   Выберите добавленный пункт меню. Обратите внимание на то, что вызывается метод в DLL-файл.

## <a name="see-also"></a>См. также

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)<br/>
[Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)
