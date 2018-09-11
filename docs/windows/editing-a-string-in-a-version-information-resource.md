---
title: Изменение строки в ресурсе сведений о версии (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources [C++]
- resources [C++], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c5cc7da4629ba00bbb1c48d764b836897c0b3748
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316982"
---
# <a name="editing-a-string-in-a-version-information-resource-c"></a>Изменение строки в ресурсе сведений о версии (C++)

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Изменение строки в ресурсе сведений о версии

1. Щелкните элемент один раз, чтобы выбрать его, а затем щелкните его повторно, чтобы приступить к редактированию. Внести изменения непосредственно в **сведения о версии** таблицы или в [окно "Свойства"](/visualstudio/ide/reference/properties-window). Внесенные изменения будут отображаться и там, и там.

   > [!NOTE] 
   > При редактировании `FILEFLAGS` в **сведения о версии** редактор, вы заметите, нельзя задать **Отладка**, **Private Build**, или **специальные Построение** свойства (в **свойства** окно) для RC-файлов:

   - **Сведения о версии** редактор задает **Отладка** свойство с `#ifdef` в сценарии ресурса, на основе `_DEBUG` флага сборки.

   - Если `Private Build` ключ имеет **значение** в **сведения о версии** таблицы, соответствующий **Private Build** свойство (в **свойства**  окно) для `FILEFLAGS` ключ будет **True**. Если **Значение** пусто, это свойство будет иметь значение **False**. Аналогичным образом **Special Build** ключ (в **сведения о версии** таблицы) привязывается к **Special Build** свойство для `FILEFLAGS` ключ.

Чтобы отсортировать строки в блоке, щелкните заголовок столбца "Раздел" или "Значение". В результате сведения автоматически будут отображаться в порядке, заданном сортировкой.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сведений о версии](../windows/version-information-editor.md)  
[Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)