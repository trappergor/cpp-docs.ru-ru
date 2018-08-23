---
title: Создание меню | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- mnemonics, associating menu items
- menus, associating commands with mnemonic keys
- menus, creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93788240ae90463c430a2d53df7e3e7f087b2c97
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596738"
---
# <a name="creating-a-menu"></a>Создание меню

> [!NOTE]
> **Окно ресурсов** недоступна в выпусках Express.

### <a name="to-create-a-standard-menu"></a>Создание стандартного меню

1. В меню **Вид** выберите пункт **Представление ресурсов** , а затем щелкните правой кнопкой мыши заголовок **Меню** и выберите команду **Добавить ресурс**. Выберите **Меню**.

2. Выберите в строке меню поле **Новый элемент** (прямоугольник с надписью "Прототип для текста").

   ![«Новый элемент» в редакторе меню](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")  
Поле "Новый элемент"

3. Введите название нового меню, например "Файл".

   Введенный текст отображается в редакторе **меню** и в поле **Заголовок** [окна свойств](/visualstudio/ide/reference/properties-window). Вы можете изменять свойства нового пункта меню в любом из этих мест.

   Как только вы присвоите название новому меню в строке меню, поле нового элемента сдвинется вправо (чтобы вы могли добавить еще одно меню), а другое поле нового элемента откроется под первым меню, чтобы вы могли добавить в него команды.

   ![Развернутое поле "новый элемент"](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")  
Поле нового элемента со смещенным фокусом после ввода названия меню

   > [!NOTE]
   > Чтобы создать меню с одним элементом в строке меню, задайте **всплывающее окно** свойства **False**.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)