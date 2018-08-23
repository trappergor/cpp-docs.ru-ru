---
title: Изменение свойство заголовка для нескольких строк | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor, changing properties of multiple strings
- strings [C++], changing caption property of multiple
- string editing, string tables
- string tables, changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 205fbd0674fa1a64ee6aeb66edfecdc1861ccba7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578376"
---
# <a name="changing-the-caption-property-of-multiple-strings"></a>Изменение свойство заголовка для нескольких строк

Ниже показано, как изменять свойство заголовка для нескольких строк.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>Чтобы изменить свойство заголовка для нескольких строк

1. Откройте таблицу строк, дважды щелкнув его значок в [представление ресурсов](../windows/resource-view-window.md).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. Выберите строки, которые вы хотите изменить, удерживая нажатой **Ctrl** ключа, щелкните каждый из них.

3. В [окно "Свойства"](/visualstudio/ide/reference/properties-window), введите новое значение для свойства, которые вы хотите изменить.

4. Нажмите клавишу **ВВОД**.

Сведения о добавлении ресурсов в управляемые проекты (предназначенные среда CLR), см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Пошаговое руководство: локализация форм Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Пошаговое руководство: использование ресурсов для локализации с ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор строк](../windows/string-editor.md)  