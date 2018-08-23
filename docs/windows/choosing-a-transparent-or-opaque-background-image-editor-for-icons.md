---
title: Выбор прозрачного и непрозрачного фона (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- opaque backgrounds
- background colors, images
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- background images
- images [C++], transparency
- images [C++], opaque background
- transparent backgrounds
- transparency, background
- transparent backgrounds, images
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd5ec3ca119b23e62fa87f1cd216d1131ae179e5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591419"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Выбор прозрачного и непрозрачного фона (Редактор изображений для значков)

При перемещении или скопировать выбранный элемент из образа, точки в выделенном фрагменте, которые соответствуют текущим цветом фона, по умолчанию являются прозрачными; они не скрывать пикселей в целевом расположении.

Можно переключиться с прозрачным фоном (по умолчанию) на непрозрачный фон и обратно. При использовании инструмента выделения, **прозрачный фон** и **непрозрачный фон** параметры отображаются в **параметр** селектор на **редактор изображений** панели инструментов (как показано ниже).

![Параметры фона &#45; прозрачный или непрозрачный](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
**Параметры прозрачности и непрозрачности** на **панель инструментов редактора изображений**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Для переключения между прозрачного и непрозрачного фона

1. В **редактор изображений** панели инструментов нажмите кнопку **параметр** селектор и затем выберите нужный фон:

   - `Opaque Background (O)`: Существующее изображение замещается все части выбранного фрагмента.

   - `Transparent Background (T)`: Существующее изображение видно части этого выбора, которые соответствуют текущим цветом фона.

\- или -

- На **изображение** меню, установите или снимите **непрозрачный**.

Можно изменить цвет фона, выбор во время эффект, который требуется изменить, какие части изображения являются прозрачными.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)  
[Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)