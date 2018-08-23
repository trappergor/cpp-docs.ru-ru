---
title: Назначение клавиш доступа командам меню | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab8ebb204b30883894e04c5d5d8a90f12c63a29b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591472"
---
# <a name="assigning-access-keys-to-menu-commands"></a>Назначение клавиш доступа командам меню

Командам меню и самим меню можно назначить клавиши доступа, позволяющие выбирать элементы меню с клавиатуры.

### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Назначение клавиши доступа (сочетания клавиш) команде меню

1. Введите знак амперсанда (`&`) перед буквой в имени меню или имя команды, чтобы указать эту букву как клавиша доступа. Например «& файл» наборы **Alt**+**F** сочетания клавиш для **файл** меню в приложениях, написанных для Microsoft Windows.

   Буква, с которой связана клавиша доступа, обычно наглядно обозначена в элементе меню. Как правило, буква, следующая за символом амперсанда, отображается как подчеркнутая (везде в рамках одной ОС).

   > [!NOTE]
   > Чтобы убедиться в том, что клавиши доступа не повторяются в рамках одного меню, щелкните меню правой кнопкой мыши и выберите в контекстном меню команду **Проверить назначенные клавиши** .

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)