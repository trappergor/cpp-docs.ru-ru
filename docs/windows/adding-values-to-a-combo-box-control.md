---
title: Добавление значений в поле со списком | Документы Microsoft
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
ms.openlocfilehash: c81e40de56970571ad78ceea86084b7ff7b82227
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="adding-values-to-a-combo-box-control"></a>Добавление значений в элемент управления поля со списком
Можно добавить значения в поле со списком, пока у вас есть открыть редактор диалоговых окон.  
  
> [!TIP]
>  Рекомендуется добавить все значения в поле со списком *перед* размера поля в редакторе диалоговых окон, или можно усекать текст, который должен отображаться в элементе управления поля со списком.  
  
#### <a name="to-enter-values-into-a-combo-box-control"></a>Для ввода значений в поле со списком  
  
1.  Выберите поле со списком, щелкнув его.  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window), прокрутите вниз до **данные** свойство.  
  
    > [!NOTE]
    >  При отображении свойств, сгруппированных по типам, **данные** отображается в **Прочее** свойства.  
  
3.  Щелкните в области значений для **данные** свойство и введите нужные значения данных, разделенных точкой с запятой.  
  
    > [!NOTE]
    >  Не следует помещать пробелы между значениями, так как пробелы влияют в алфавитном порядке в раскрывающемся списке.  
  
4.  Нажмите кнопку **ввод** при завершении добавления значений.  
  
 Сведения об увеличении раскрывающаяся часть поля со списком см. в разделе [задание размера для поля со списком и раскрывающегося списка, его](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).  
  
> [!NOTE]
>  Нельзя добавлять значения в проекты Win32, с помощью этой процедуры ( **данные** свойство является недоступным для проектов Win32). Поскольку проекты Win32 нет библиотеки, поддерживающие эту возможность, необходимо добавить значения в поле со списком в проекте Win32 программными средствами.  
  
#### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>Для проверки значений в поле со списком  
  
1.  После ввода значения в **данные** свойства, нажмите кнопку **теста** кнопку [инструментов редактора диалоговых окон](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
     Попробуйте прокрутить весь список значений. Значения отображаются в точности так, как они были введены в **данные** в окне свойств. Нет проверки орфографии или проверка регистр букв.  
  
     Нажмите клавишу ESC, чтобы вернуться в редактор диалоговых окон.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)

