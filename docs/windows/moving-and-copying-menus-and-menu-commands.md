---
title: Перемещение и копирование меню и команд меню | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc95eef2c3cca678ae291846c2ebe0e5c1e80997
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609086"
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>Перемещение и копирование меню и команд меню

Вы можете перемещать или копировать меню и команды меню с помощью метода перетаскивания или с помощью команд контекстного меню (щелкните правой кнопкой мыши меню).

### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>Перемещение или копирование меню или команд меню с помощью метода перетаскивания

1. Перетащите или скопируйте элемент, который требуется переместить.

   - Новое расположение в текущем меню.

   - Другое меню. (Можно перейти к другим меню, перетащив на них указатель мыши.)

2. Удалите команды меню, когда направляющая покажет нужное положение.

### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>Перемещение или копирование меню или команд меню с помощью команд контекстного меню

1. Щелкните правой кнопкой мыши одно или несколько меню или команд меню.

2. В контекстном меню выберите **Вырезать** (для перемещения) или **Копировать**.

3. При перемещении элементов в другой ресурс меню ресурса или файл описания ресурсов [откройте его в другом окне](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

4. Выберите положение меню или команды меню, которую нужно переместить или скопировать.

5. Выберите в контекстном меню команду **Вставить**. Перемещенный или скопированный пункт помещается перед выбранным пунктом.

   > [!NOTE]
   > Вы также можете перетаскивать, копировать и вставлять в другие меню в других окнах меню.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)