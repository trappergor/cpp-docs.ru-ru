---
title: Редактирование двоичных данных | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- binary data
ms.assetid: 0fd429de-baf1-4871-b5e4-42bf868a3261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96a4370d56e2f5d9758e97010965668bd08306c3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593009"
---
# <a name="editing-binary-data"></a>Редактирование двоичных данных

### <a name="to-edit-a-resource-in-the-binary-editor"></a>Изменение ресурса в двоичном редакторе

1. Выберите байт, который требуется изменить.

   **Вкладке** фокус перемещается клавишей между шестнадцатеричном формате и ASCII-разделом **двоичных** редактора. Можно использовать **Page Up** и **Page Down** ключи для перемещения по ресурсу на один экран за раз.

2. Введите новое значение.

   Значение сразу изменится в шестнадцатеричном формате и ASCII разделы, а фокус перемещается к следующему значению в строке.

   > [!NOTE]
   > **Двоичных** редактор автоматически применяет изменения при закрытии редактора.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Нет

## <a name="see-also"></a>См. также

[Binary Editor](binary-editor.md)