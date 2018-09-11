---
title: Изменение свойство заголовка для нескольких строковых ресурсов (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b2ba75745d769d593549e707a9100a50c40e6f65
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318828"
---
# <a name="changing-the-caption-property-of-multiple-string-resources-c"></a>Изменение свойство заголовка для нескольких строковых ресурсов (C++)

Ниже показано, как изменять свойство заголовка для нескольких строк.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>Чтобы изменить свойство заголовка для нескольких строк

1. Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите строки, которые вы хотите изменить, удерживая нажатой **Ctrl** ключа, щелкните каждый из них.

3. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), введите новое значение для свойства, которые вы хотите изменить.

4. Нажмите клавишу **ВВОД**.

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)  