---
title: 'Практическое: создать ресурс (C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 23717c35d0590c88a4904e5b6b6ddb0e4c7ccffc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071976"
---
# <a name="how-to-create-a-resource"></a>Практическое руководство. Создание ресурса

> [!NOTE]
> **Представление ресурсов** не поддерживается в выпусках Express.

### <a name="to-create-a-new-resource-in-resource-view"></a>Создание ресурса в представлении ресурсов

1. Установив фокус на RC-файл в [представление ресурсов](../windows/resource-view-window.md), нажмите кнопку **изменить** меню и выберите **добавить ресурс** (или щелкните правой кнопкой мыши RC-файл в **представление ресурсов** и выберите **добавить ресурс** в контекстном меню).

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.

### <a name="to-create-a-new-resource-in-solution-explorer"></a>Создание ресурса в обозревателе решений

1. В **обозревателе решений**щелкните правой кнопкой мыши папку проекта, выберите в контекстном меню команду **Добавить**, а затем выберите пункт **Добавить ресурс** .

   Если в вашем проекте еще нет RC-файла, на этом шаге он будет создан. Затем можно повторить этот шаг, чтобы добавить конкретные типы ресурсов в новый RC-файл.

2. В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.

### <a name="to-create-a-new-resource-in-class-view"></a>Создание ресурса в представлении классов

1. В [представлении классов](/visualstudio/ide/viewing-the-structure-of-code)щелкните правой кнопкой мыши нужный класс, выберите в контекстном меню команду **Добавить**, а затем выберите пункт **Добавить ресурс** .

2. В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.

### <a name="to-create-a-new-resource-from-the-project-menu"></a>Создание ресурса из меню "Проект"

1. В меню **Проект** выберите команду **Добавить ресурс**.

При создании нового ресурса Visual C++ назначает уникальное имя, например, `IDD_Dialog1`. Этот идентификатор ресурса можно изменить путем редактирования свойств ресурса в соответствующем редакторе или в [окне свойств](/visualstudio/ide/reference/properties-window).

Вы можете создать ресурс как новый ресурс с параметрами по умолчанию (ресурс, созданный не по шаблону) или как ресурс на основе [шаблона](../windows/how-to-use-resource-templates.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Редакторы ресурсов](../windows/resource-editors.md)<br/>
[Add Resource Dialog Box](../windows/add-resource-dialog-box.md)