---
title: Выбор прозрачного и непрозрачного фона (редактор изображений для значков) | Документы Microsoft
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
ms.openlocfilehash: 244e6a63bc16b5e83bb8419dbe1b53741d566e56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857916"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Выбор прозрачного и непрозрачного фона (Редактор изображений для значков)
При перемещении или копировании выбор из образа, точки в целевом, которые соответствуют текущим цветом фона, по умолчанию являются прозрачной. они не мешает пикселей в целевом расположении.  
  
 Переключение непрозрачный фон с прозрачным фоном (по умолчанию) и обратно. При использовании средства выбора **прозрачный фон** и **непрозрачный фон** параметры отображаются в селекторе параметров на **редактора изображений** панель инструментов (как показано ниже).  
  
 ![Параметры фона &#45; прозрачный или непрозрачный](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
Параметры прозрачности и непрозрачности на панели инструментов редактора изображений  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Для переключения между прозрачного и непрозрачного фона  
  
1.  В **редактора изображений** инструментов, нажмите кнопку **параметр** селектора и затем выберите нужный фон:  
  
    -   **Непрозрачный фон (O)**: существующее изображение замещается все части выбранного фрагмента.  
  
    -   **Прозрачный фон (T)**: существующее изображение видно сквозь части выбранного фрагмента, которые соответствуют текущим цветом фона.  
  
 \- или -  
  
-   На **изображения** меню, установите или снимите **непрозрачный**.  
  
 Можно изменить цвет фона, во время выделения уже находится в определяющей, какие части изображения являются прозрачными.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)