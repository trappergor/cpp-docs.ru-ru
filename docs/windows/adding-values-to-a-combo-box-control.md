---
title: Добавление значений в поле со списком | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [Visual Studio], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- controls [C++], testing values in combo boxes
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1727313018e88d97f810204428cc99f7aab2366
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591613"
---
# <a name="adding-values-to-a-combo-box-control"></a>Добавление значений в элемент управления поля со списком

Можно добавить значения в поле со списком, до тех пор, пока у вас есть **диалоговое окно** в редакторе.

> [!TIP]
> Рекомендуется добавить все значения в поле со списком *перед* размера поля в **диалоговое окно** редактора, или может обрезать текст, который должен отображаться в элементе управления поля со списком.

### <a name="to-enter-values-into-a-combo-box-control"></a>Для ввода значений в поле со списком

1. Выберите поле со списком, щелкнув его.

2. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), прокрутите вниз до раздела **данных** свойство.

   > [!NOTE]
   > При отображении свойства, сгруппированных по типам, **данных** отображается в **Прочее** свойства.

3. Щелкните в области значений для **данных** свойство и введите нужные значения данных, разделенных точкой с запятой.

   > [!NOTE]
   > Не вставляйте пробелы между значениями, так как пробелы влияют в алфавитном порядке в раскрывающемся списке.

4. Нажмите кнопку **ввод** при завершении добавления значений.

Сведения об увеличении раскрывающаяся часть поля со списком, см. в разделе [задание размера для поля со списком и его с раскрывающимся списком](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).

> [!NOTE]
> Проекты Win32, с помощью этой процедуры нельзя добавлять значения ( **данных** свойство является недоступным для проектов Win32). Поскольку проекты Win32 не имеют библиотеки, поддерживающие эту возможность, необходимо добавить значения в поле со списком в проекте Win32 программным способом.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Проверка значений в поле со списком

1. После ввода значений в **данных** свойство, нажмите кнопку **теста** кнопку [редактор диалоговых окон инструментов](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

   Попробуйте прокрутить список всего значения. Значения отображаются точно так, как они были введены в **данных** свойство в **свойства** окна. Нет, написание или проверка регистр букв.

   Нажмите клавишу **Esc** для возврата **диалоговое окно** редактора.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы управления](../mfc/controls-mfc.md)