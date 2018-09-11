---
title: Изменение масштаба увеличения (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], magnification
ms.assetid: d1b0c9e0-fe54-4b2a-b75e-ffa0fa7c8cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 561c5c46d0486718cbe05af1507459c26babea8b
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315279"
---
# <a name="changing-the-magnification-factor-image-editor-for-icons"></a>Изменение масштаба увеличения (редактор изображений для значков)

По умолчанию редактор изображений отображает представление в области слева в фактический размер и представление в области справа в 6 раз больше фактического размера. Масштаб (показано в строке состояния в нижней части рабочей области) — это отношение между фактический размер образа и отображаемый размер. По умолчанию коэффициент равен 6, а диапазон — от 1 до 10.

### <a name="to-change-the-magnification-factor"></a>Чтобы изменить масштаб

1. Выберите **редактор изображений** область, масштаб которых вы хотите изменить.

2. На [панель инструментов редактора изображений](../windows/toolbar-image-editor-for-icons.md), щелкните стрелку справа от [инструмента увеличить](../windows/toolbar-image-editor-for-icons.md) и выберите масштаб увеличения в подменю: **1 X**, **2 X**, **6 X**, или **8 X**.

   > [!NOTE]
   > Чтобы выбрать масштаб, отличного от перечисленных в **увеличить** инструмент, использовать сочетания клавиш.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  
[Области окна](../windows/window-panes-image-editor-for-icons.md)