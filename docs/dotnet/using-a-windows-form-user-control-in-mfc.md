---
title: С помощью Windows формы пользовательского элемента управления в MFC | Документы Microsoft
ms.custom: ''
ms.date: 1/08/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ceb424d6c5061ac5ccafc62d8748be4de3ab3d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Использование пользовательского элемента управления формы Windows Form в MFC

С помощью вспомогательных классов MFC Windows Forms, может содержать элементы управления Windows Forms в приложениях MFC как элемент управления ActiveX в диалоговые окна MFC или представления. Кроме того как диалоговые окна MFC можно разместить форм Windows Forms.

В следующих разделах описаны способы:

- Размещение элемента управления Windows Forms в диалоговом окне MFC.

- Разместить пользовательский элемент управления Windows Forms в качестве представления MFC.

- Разместить форму Windows Forms в диалоговом окне MFC.

> [!NOTE]
> Интеграция MFC Windows Forms работает только в тех проектах, которые динамически связываются с MFC (проекты, в котором `_AFXDLL` определен).

> [!NOTE]
> При построении приложения (изменено) частную копию библиотеки DLL (файл mfcmifc80.dll) интерфейсов MFC Windows Forms с помощью его не удастся установить в глобальном кэше СБОРОК, если ключ Майкрософт замените свой собственный ключ поставщика. Дополнительные сведения о подписи сборки см. в разделе [программирование с использованием сборок](/dotnet/framework/app-domains/programming-with-assemblies) и [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Образцы приложений с помощью Windows Forms, см. [BirthdayPicker образец: демонстрируется ресурсы платформы .NET с помощью Windows Forms](http://msdn.microsoft.com/ac932aed-5502-4667-be29-709bca435317), [образец калькулятора: Windows Forms карманного калькулятора](http://msdn.microsoft.com/2283b516-3b7e-45f2-80c4-fdcfb366ce25)и [ Образец SCRIBBLE: Приложение для рисования MDI](http://msdn.microsoft.com/f025da3e-659b-4222-b991-554a1b8b2358).

Образец приложения Windows Forms используются с MFC, в разделе [MFC и интеграция с Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).

Если приложение MFC использует Windows Forms, необходимо повторно распространить файл mfcmifc80.dll вместе с приложением. Дополнительные сведения см. в разделе [распространение библиотеки MFC](../ide/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>В этом разделе

[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Ссылка

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)

[Класс CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md)

[Класс CWinFormsView](../mfc/reference/cwinformsview-class.md)

[Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)

[Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)

[Интерфейс ICommandUI](../mfc/reference/icommandui-interface.md)

[Интерфейс IView](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>Связанные разделы

[Windows Forms](/dotnet/framework/winforms/index)

[Элементы управления Windows Forms](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)  
[Представления форм](../mfc/form-views-mfc.md)  
