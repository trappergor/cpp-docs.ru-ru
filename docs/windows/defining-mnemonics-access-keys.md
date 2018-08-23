---
title: Определение клавиш доступа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 084b9a84f7a113458ca1cf76549b865d019216cc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613440"
---
# <a name="defining-mnemonics-access-keys"></a>Определение клавиш доступа

Как правило, пользователи перемещают фокус ввода от одного элемента управления на другой в диалоговое окно с **вкладке** и **стрелку** ключи. Тем не менее можно определить ключ доступа (сокращение или легко запоминаемых имя), который позволяет пользователю выбрать элемент управления, нажав один ключ.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Чтобы определить ключ доступа для элемента управления в видимом заголовке (кнопки, флажки и переключатели)

1. Выберите элемент управления в диалоговом окне.

2. В [окно "Свойства"](/visualstudio/ide/reference/properties-window)в **заголовок** свойство, введите новое имя для элемента управления, введя амперсанд (`&`) перед буквой, как клавиша доступа для этого элемента управления. Например, `&Radio1`.

3. Нажмите клавишу **ВВОД**.

   Подчеркивается в отображаемом заголовке, чтобы указать ключ доступа, например, **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Чтобы определить ключ доступа для элемента управления без видимого заголовка

1. Создайте заголовок для элемента управления с помощью **статический текст** контролировать [элементов](/visualstudio/ide/reference/toolbox).

2. В заголовке статического текста, введите знак амперсанда (`&`) перед буквой, как клавиша доступа.

3. Убедитесь, что управление статическим текстом непосредственно предшествует элементу статического в последовательности табуляции.

Все ключи доступа в диалоговом окне должно быть уникальным.

### <a name="to-check-for-duplicate-access-keys"></a>Для проверки дублирующиеся клавиши доступа

1. На **формат** меню, щелкните **проверить назначенные клавиши**.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы управления](../mfc/controls-mfc.md)