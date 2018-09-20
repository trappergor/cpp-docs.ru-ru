---
title: Задание главного элемента управления | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dominant controls
- Dialog Editor [C++], dominant control
- controls [C++], dominant
ms.assetid: 42b523a7-192a-417b-9512-d4af795e002f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31bb19a0854bd28573d474a65781808eaecd7ce2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407573"
---
# <a name="specifying-the-dominant-control"></a>Задание главного элемента управления

Во-первых, выбранного элемента управления является главного элемента управления.

### <a name="to-specify-the-dominant-control"></a>Чтобы указать главного элемента управления

1. Удерживая нажатой **Ctrl** ключа и щелкните элемент управления, который вы хотите использовать, чтобы повлиять на размер или расположение других элементов управления *первый*.

   **Примечание** маркеры главного элемента управления показываются сплошными, а маркеры подчиненных элементов управления являются пустыми. Все дальнейшее изменение размера или выравнивание зависит от главного элемента управления.

### <a name="to-change-the-dominant-control"></a>Изменение главного элемента управления

1. Очистите текущее выделение, щелкнув за пределами всех выбранных элементов управления.

2. Повторите предыдущую процедуру, сначала выбрав другой элемент управления.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Выбор нескольких элементов управления](../windows/selecting-multiple-controls.md)<br/>
[Выбор элементов управления](../windows/selecting-controls.md)<br/>
[Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)