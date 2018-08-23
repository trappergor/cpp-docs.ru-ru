---
title: Задание ширины горизонтальной полосы прокрутки | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64dd7bea162839642a10253baddfc7abbe9eb802
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612416"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>Задание ширины горизонтальной полосы прокрутки

При добавлении полем со списком с горизонтальной полосы прокрутки в диалоговое окно, с помощью классов MFC, полоса прокрутки не появится автоматически в приложении.

### <a name="to-make-the-scroll-bar-appear"></a>Чтобы сделать отображение полосы прокрутки

1. Задать максимальную ширину для элемента широкой, вызвав [CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent) в коде.

   Без указания этого значения полоса прокрутки не появится, даже если элементы в поле со списком имеют шире, чем поле.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)  
[Элементы управления](../mfc/controls-mfc.md)