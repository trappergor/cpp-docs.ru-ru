---
title: "Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Маршрутизация команд [C++], добавление к элементам управления Windows Forms"
  - "Элементы управления Windows Forms [C++], команда маршрутизации"
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Практическое руководство. Добавление маршрутизации команд в элемент управления Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView](../mfc/reference/cwinformsview-class.md) направляет команды и сообщения пользовательского Интерфейса команды update в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов).  
  
 Пользовательский элемент управления использует [ICommandTarget::Initialize](../Topic/ICommandTarget::Initialize.md) для хранения ссылки на объект источника команды в `m_CmdSrc`, как показано в следующем примере. Для использования `ICommandTarget` необходимо добавить ссылку на библиотеку mfcmifc80.dll.  
  
 `CWinFormsView` обрабатывает несколько общих уведомлений MFC, перенаправляя их в управляемый пользовательский элемент управления. Эти уведомления включают [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) и [OnActivateView](../Topic/IView::OnActivateView.md) методы [интерфейс IView](../Topic/IView%20Interface.md).  
  
 В этом разделе предполагается, что Вы завершили ранее [Практическое руководство: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) и [как: Создание пользовательского элемента управления и представление главного приложения MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>Создание ведущего приложения MFC  
  
1.  Открытие библиотеки элементов управления Windows Forms, созданный в [Практическое руководство: Создание пользовательского элемента управления и ведущего приложения в диалоговом окне](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  Добавьте ссылку на библиотеку mfcmifc80.dll, можно сделать, щелкнув правой кнопкой мыши узел проекта в **обозревателе**, выбрав **Добавить**, **ссылку**, и затем перейдите в Microsoft Visual Studio 10.0\VC\atlmfc\lib.  
  
3.  Откройте файл UserControl1.Designer.cs и добавьте следующий оператор using:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  Кроме того в файл UserControl1.Designer.cs, измените следующую строку:  
  
    ```  
    partial class UserControl1  
    ```  
  
     для этого:  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  Добавить в качестве первой строки определения класса `UserControl1`:  
  
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
  
7.  Откройте приложение MFC, созданный в [Практическое руководство: Создание пользовательского элемента управления и представление главного приложения MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Добавьте пункт меню, который будет вызывать `singleMenuHandler`.  
  
     Последовательно выберите пункты **ресурсов** (Ctrl + Shift + E), разверните **меню** папку и дважды щелкните **IDR_MFC02TYPE**. Откроется редактор меню.  
  
     Добавьте пункт меню в нижней части **представление** меню. Обратите внимание на идентификатор пункта меню в **Свойства** окна. Сохраните файл.  
  
     В **обозревателе**, откройте файл Resource.h, скопируйте значение идентификатора для добавленного пункта меню и вставьте это значение в качестве первого параметра для `m_CmdSrc.AddCommandHandler` вызова в проекте C# `Initialize` метод (заменив `32771` при необходимости).  
  
9. Постройте и запустите проект.  
  
     В меню **Сборка** выберите **Собрать решение**.  
  
     На **отладки** меню, щелкните **Запуск без отладки**.  
  
     Выберите добавленный пункт меню. Обратите внимание, что вызывается метод в DLL-файл.  
  
## <a name="see-also"></a>См. также раздел  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)   
 [Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)