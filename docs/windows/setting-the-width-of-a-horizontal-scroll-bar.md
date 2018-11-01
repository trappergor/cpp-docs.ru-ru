---
title: Задание ширины горизонтальной полосы прокрутки
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [C++], scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars [C++], displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars [C++], width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
ms.openlocfilehash: 393571b79d27485e840d150549208c899e8ed1d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625957"
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

[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)