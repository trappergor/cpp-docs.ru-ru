---
title: 'Практическое: поиск символов в ресурсах (C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 51b2045a1605a37fa9c0d17fdc0c9456652345bd
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314200"
---
# <a name="how-to-search-for-symbols-in-resources-c"></a>Практическое: поиск символов в ресурсах (C++)

### <a name="to-find-symbols-in-resources"></a>Поиск символов в ресурсах

1. Из **изменить** меню, выберите **поиск символа**.

2. В [поиск символа-диалоговое окно](/visualstudio/ide/go-to)в **найти** выберите предыдущую строку поиска из раскрывающегося списка или введите сочетание клавиш, которое требуется найти (например, ID_ACCEL1).

   > [!TIP]
   > Для использования [регулярные выражения](/visualstudio/ide/using-regular-expressions-in-visual-studio) для поиска, необходимо использовать [команда Find in Files](/visualstudio/ide/reference/find-command) из **изменить** меню вместо **поиск символа**команды. Чтобы включить регулярные выражения, необходимо иметь **использования: регулярные выражения** флажком в [диалоговое окно «Найти»](/visualstudio/ide/finding-and-replacing-text). Затем можно щелкнуть кнопку со стрелкой вправо, справа от **найти** поле, чтобы отобразить список регулярных выражений для поиска. При выборе выражения из этого списка оно подставляется как текст для поиска в **найти** поле.

3. Выберите любой из **найти** параметры.

4. Нажмите кнопку **Найти далее**.

   > [!NOTE]
   > Нельзя выполнять поиск символов в строках, сочетаниях клавиш и двоичных ресурсах.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам отображать статические ресурсы и назначение ресурсов строки свойства.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Символы: идентификаторы ресурсов](../windows/symbols-resource-identifiers.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)