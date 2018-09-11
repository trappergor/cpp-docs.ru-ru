---
title: Отключение направляющих | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, disabling snapping
- Dialog editor [C++], snap to guides
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
ms.assetid: 51efa07b-8684-474e-a0b4-191ec5d91d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e3ae2e982ce04743644f9c94d9c163478c0b67e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313121"
---
# <a name="disabling-guides"></a>Отключение направляющих

Отключение эффекта привязки руководства можно использовать специальные ключи в сочетании с помощью мыши. С помощью **Alt** ключ отключает эффект привязки для выбранной направляющей. Перемещение направляющей при **Shift** ключа не позволяет перемещать со структурой привязанных элементов управления.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>Отключение эффекта привязки направляющие

1. Перетащите элемент управления, удерживая нажатой **Alt** ключ.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Перемещение направляющих без перемещения привязанных элементов управления

1. Перетащите направляющую, удерживая нажатой **Shift** ключ.

### <a name="to-turn-off-the-guides"></a>Чтобы отключить направляющие

1. Из **формат** меню, выберите **параметры направляющих**.

2. В [диалоговое окно "Параметры направляющих"](../windows/guide-settings-dialog-box.md)в разделе **направляющих макета**выберите **None**.

   > [!NOTE]
   > Можно также дважды щелкнуть строку линейки, чтобы получить доступ к **параметры направляющих** диалоговое окно.

\- или -

- На **формат** меню, щелкните **направляющие**.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Состояния редактора диалоговых окон (направляющие и сетки)](../windows/dialog-editor-states-guides-and-grids.md)  
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)