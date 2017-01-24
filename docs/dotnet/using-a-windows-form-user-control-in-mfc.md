---
title: "Использование пользовательского элемента управления формы Windows Form в MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Поддержка Windows Forms MFC [C++]"
  - "взаимодействие [C++], Windows Forms в MFC"
  - "взаимодействие [C++], MFC"
  - "взаимодействие [C++], Windows Forms в MFC"
  - "взаимодействие [C++], MFC"
  - "Поддержка Windows Forms [C++] MFC"
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование пользовательского элемента управления формы Windows Form в MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью классов поддержки MFC Windows Forms, можно размещать элементы управления Windows Forms в приложениях MFC как элемент управления ActiveX в диалоговые окна MFC или представления. Кроме того форм Windows Forms можно разместить как диалоговые окна MFC.  
  
 В следующих разделах описаны способы:  
  
-   Размещение элемента управления Windows Forms в диалоговом окне MFC.  
  
-   Размещение пользовательского элемента управления Windows Forms как представления MFC.  
  
-   Размещать форму Windows Forms в диалоговом окне MFC.  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (проекты, в которых определена AFXDLL).  
  
> [!NOTE]
>  При построении приложения с использованием закрытой (изменено) копии интерфейсов MFC Windows Forms DLL (библиотеки mfcmifc80.dll) не сможет установить в глобальном кэше СБОРОК, если ключ Майкрософт заменить ключ поставщика. Дополнительные сведения о подписи сборки см. в разделе [программирование с использованием сборок](../Topic/Programming%20with%20Assemblies.md) и [сборки строгим именем (подписывание сборок) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Примеры приложений с помощью Windows Forms, см. [BirthdayPicker образец: демонстрируется ресурсы платформы .NET с помощью Windows Forms](http://msdn.microsoft.com/ru-ru/ac932aed-5502-4667-be29-709bca435317), [Образец калькулятора: карманный калькулятор Windows Forms](http://msdn.microsoft.com/ru-ru/2283b516-3b7e-45f2-80c4-fdcfb366ce25), и [образец Scribble: рисование MDI-приложения](http://msdn.microsoft.com/ru-ru/f025da3e-659b-4222-b991-554a1b8b2358).  
  
 Образец приложения Windows Forms используются с MFC, в разделе [MFC и Windows Forms Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Если приложение MFC использует Windows Forms, необходимо распространить библиотеку mfcmifc90.dll вместе с приложением. Дополнительные сведения см. в разделе [распространение библиотеки MFC](../ide/redistributing-the-mfc-library.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Размещение элемента управления формы пользователя Windows в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [Размещение пользовательского элемента управления формы Windows Form в диалоговом окне MFC](../Topic/Hosting%20a%20Windows%20Form%20User%20Control%20as%20an%20MFC%20Dialog%20Box.md)  
  
## <a name="reference"></a>Ссылка  
 [Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)  
  
 [Класс CWinFormsDialog](../Topic/CWinFormsDialog%20Class.md)  
  
 [Класс CWinFormsView](../mfc/reference/cwinformsview-class.md)  
  
 [Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)  
  
 [Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)  
  
 [Интерфейс ICommandUI](../mfc/reference/icommandui-interface.md)  
  
 [Интерфейс IView](../Topic/IView%20Interface.md)  
  
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)  
  
 [CommandUIHandler](../Topic/CommandUIHandler%20Delegate.md)  
  
 [DDX_ManagedControl](../Topic/DDX_ManagedControl.md)  
  
 [UICheckState](../Topic/UICheckState%20Enumeration.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 [Windows Forms](../Topic/Windows%20Forms.md)  
  
 [Элементы управления Windows Forms](../Topic/Windows%20Forms%20Controls.md)  
  
 [Пользовательские элементы управления ASP.NET](../Topic/ASP.NET%20User%20Controls.md)  
  
## <a name="see-also"></a>См. также раздел  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Представления форм](../Topic/Form%20Views%20\(MFC\).md)