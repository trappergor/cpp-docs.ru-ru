---
title: 'Как: Добавление команды управления маршрутизации в Windows Forms | Документы Microsoft'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c13b0bedf7c81431449aaed8d4fa8f067cdf3d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms
[CWinFormsView](../mfc/reference/cwinformsview-class.md) направляет команды и сообщения пользовательского интерфейса команды update в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов).  
  
 Пользовательский элемент управления использует [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) для хранения ссылки на объект источника команды в `m_CmdSrc`, как показано в следующем примере. Для использования `ICommandTarget` необходимо добавить ссылку на библиотеку mfcmifc80.dll.  
  
 `CWinFormsView` обрабатывает несколько общих уведомлений MFC, перенаправляя их в управляемый пользовательский элемент управления. Эти уведомления включают [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) и [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) методы.  
  
 В этом разделе предполагается, вы выполнили ранее [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Открытие библиотеки элементов управления Windows Forms, созданный в [как: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  Добавьте ссылку на библиотеку mfcmifc80.dll, это можно сделать, щелкнув правой кнопкой мыши узел проекта в **обозревателе решений**, выбрав **добавить**, **ссылки**и затем перейдите в Microsoft Visual Studio 10.0\VC\atlmfc\lib.  
  
3.  Откройте файл UserControl1.Designer.cs и добавьте следующий код с помощью инструкции:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  Кроме того в файл UserControl1.Designer.cs, измените следующую строку:  
  
    ```  
    partial class UserControl1  
    ```  
  
     на эту:  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  Добавить в качестве первой строки в определении класса для `UserControl1`:  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  Добавьте следующие определения метода в `UserControl1` (в следующем шаге создается идентификатор элемента управления MFC):  
  
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
  
7.  Откройте приложение MFC, созданные в [как: Создание пользовательского элемента управления и просмотр ведущего интерфейса MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Добавьте пункт меню, который будет вызывать `singleMenuHandler`.  
  
     Последовательно выберите пункты **представление ресурсов** (Ctrl + Shift + E), разверните **меню** папку и дважды щелкните **IDR_MFC02TYPE**. Откроется редактор меню.  
  
     Добавьте пункт меню в нижней части **представление** меню. Обратите внимание, идентификатор пункта меню в **свойства** окна. Сохраните файл.  
  
     В **обозревателе решений**, откройте файл Resource.h, скопируйте значение идентификатора для добавленного пункта меню и вставьте это значение в качестве первого параметра в `m_CmdSrc.AddCommandHandler` вызов в проект C# `Initialize` метод (заменив `32771` при необходимости).  
  
9. Постройте и запустите проект.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, нажмите кнопку **Запуск без отладки**.  
  
     Выберите добавленный пункт меню. Обратите внимание, что вызывается метод в DLL-файл.  
  
## <a name="see-also"></a>См. также  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Интерфейс руководство.](../mfc/reference/icommandsource-interface.md)   
 [Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](http://msdn.microsoft.com/Library/22096734-e074-4aca-8523-4b15590109f9)