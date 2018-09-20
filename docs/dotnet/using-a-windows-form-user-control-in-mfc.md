---
title: С помощью Windows форме пользовательского элемента управления в MFC | Документация Майкрософт
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
ms.openlocfilehash: 4fef169cb0e2386c1629064ad7ea8a1a70a5c517
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382080"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>Использование пользовательского элемента управления формы Windows Form в MFC

С помощью вспомогательных классов MFC Windows Forms, можно разместить элементы управления Windows Forms в приложениях MFC как элемент управления ActiveX в диалоговых окнах MFC или представления. Кроме того форм Windows forms можно разместить как диалоговые окна MFC.

В следующих разделах описываются как:

- Размещение элемента управления Windows Forms в диалоговом окне MFC.

- Разместить пользовательский элемент управления Windows Forms в качестве представления MFC.

- Размещать форму Windows Forms в диалоговом окне MFC.

> [!NOTE]
> Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (проекты, в котором `_AFXDLL` определен).

> [!NOTE]
> При создании приложения с помощью (изменено) частную копию интерфейсов MFC Windows Forms DLL (библиотеку mfcmifc80.dll), он не сможет установить в глобальном кэше СБОРОК, если ключ Майкрософт замените свой собственный ключ поставщика. Дополнительные сведения о подписи сборки см. в разделе [программирование с использованием сборок](/dotnet/framework/app-domains/programming-with-assemblies) и [сборки со строгими именами (подписывание сборок) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Если приложение MFC использует Windows Forms, необходимо повторно распространить библиотеку mfcmifc80.dll с вашим приложением. Дополнительные сведения см. в разделе [распространение библиотеки MFC](../ide/redistributing-the-mfc-library.md).

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

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Представления форм](../mfc/form-views-mfc.md)
