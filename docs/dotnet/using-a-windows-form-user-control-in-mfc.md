---
title: Использование пользовательского элемента управления формы Windows Form в MFC
ms.date: 01/08/2018
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
ms.openlocfilehash: efabbf84778d925ec1de03f5f4ea0ca09185bd81
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "79544750"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Использование пользовательского элемента управления формы Windows Form в MFC

С помощью классов поддержки MFC Windows Forms можно размещать элементы управления Windows Forms в приложениях MFC в виде элемента управления ActiveX в диалоговых окнах или представлениях MFC. Кроме того, Windows Forms формы могут размещаться в виде диалоговых окон MFC.

В следующих разделах описывается:

- Размещение элемента управления Windows Forms в диалоговом окне MFC.

- Размещение пользовательского элемента управления Windows Forms как представления MFC.

- Размещение Windows Forms формы в виде диалогового окна MFC.

> [!NOTE]
> Интеграция с MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (проектами, в которых определен `_AFXDLL`).

> [!NOTE]
> При сборке приложения с помощью закрытой (измененной) копии библиотеки DLL Windows Formsных интерфейсов MFC (mfcmifc80. dll) она не будет установлена в глобальном кэше сборок, если вы не замените ключ Майкрософт своим ключом поставщика. Дополнительные сведения о подписывании сборок см. в разделе [программирование со сборками](/dotnet/framework/app-domains/programming-with-assemblies) и [сборками со строгими именамиC++(подписывание сборок) (/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Если приложение MFC использует Windows Forms, необходимо повторно распространить mfcmifc80. dll вместе с приложением. Дополнительные сведения см. [в разделе распространение библиотеки MFC](../windows/redistributing-the-mfc-library.md).

## <a name="in-this-section"></a>в этом разделе

[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[Размещение пользовательского элемента управления формы Windows Forms в качестве представления MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[Размещение пользовательского элемента управления формы Windows Forms в диалоговом окне MFC](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>Ссылки

[Класс CWinFormsControl](../mfc/reference/cwinformscontrol-class.md)

[Класс CWinFormsDialog](../mfc/reference/cwinformsdialog-class.md)

[Класс CWinFormsView](../mfc/reference/cwinformsview-class.md)

[Интерфейс ICommandSource](../mfc/reference/icommandsource-interface.md)

[Интерфейс ICommandTarget](../mfc/reference/icommandtarget-interface.md)

[Интерфейс ICommandUI](../mfc/reference/icommandui-interface.md)

[Интерфейс IView](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[уичеккстате](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>Связанные разделы

[Windows Forms](/dotnet/framework/winforms/index)

[Элементы управления Windows Forms](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>См. также:

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Представления формы](../mfc/form-views-mfc.md)
