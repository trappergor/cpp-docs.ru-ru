---
title: Преобразование изображения из одного формата в другой (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], stand-alone editing
- Image editor [C++], converting image formats
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 0409c2bd-3bd8-4d72-9c71-c683b6cf51be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ef3a2ce99309781ecbfd0c406fe8e0f6f7e0613
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592122"
---
# <a name="converting-an-image-from-one-format-to-another-image-editor-for-icons"></a>Преобразование изображения из одного формата в другой (редактор изображений для значков)

Вы можете открыть изображений GIF или JPEG в **изображение** редактора и сохранения их в виде точечных рисунков. Кроме того можно открыть файл точечного рисунка и сохраните его в формате GIF или JPEG. Изображения не обязательно входят в проект для редактирования в среде разработки (см. в разделе [редактирование автономного образа](../windows/editing-an-image-outside-of-a-project-image-editor-for-icons.md)).

### <a name="to-convert-an-image-from-one-format-to-another"></a>Преобразование изображения из одного формата в другой

1. Открывать изображение в **изображение** редактора.

2. Из **файл** меню, выберите **Сохранить *filename* как**.

3. В **сохранить файл как** отображаемое в диалоговом окне **имя файла** введите имя файла и расширение, которое обозначает необходимый формат.

4. Нажмите кнопку **Сохранить**.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Редактор изображений для значков](../windows/image-editor-for-icons.md)