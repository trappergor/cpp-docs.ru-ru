---
title: 'Как: создать ресурс | Документы Microsoft'
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
- resources [Visual Studio], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3a5c8ee47203f24c1995cfde9dda40912f21467
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878649"
---
# <a name="how-to-create-a-resource"></a>Практическое руководство. Создание ресурса
> [!NOTE]
>  Просмотр ресурсов не поддерживается в выпусках Express.  
  
### <a name="to-create-a-new-resource-in-resource-view"></a>Создание ресурса в представлении ресурсов  
  
1.  Установив фокус на RC-файл в [представлении ресурсов](../windows/resource-view-window.md), выберите команду меню **Изменить** , а затем выберите пункт **Добавить ресурс** (или щелкните правой кнопкой мыши RC-файл в представлении ресурсов и выберите в контекстном меню команду **Добавить ресурс** ).  
  
     **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.  
  
### <a name="to-create-a-new-resource-in-solution-explorer"></a>Создание ресурса в обозревателе решений  
  
1.  В **обозревателе решений**щелкните правой кнопкой мыши папку проекта, выберите в контекстном меню команду **Добавить**, а затем выберите пункт **Добавить ресурс** .  
  
     Если в вашем проекте еще нет RC-файла, на этом шаге он будет создан. Затем можно повторить этот шаг, чтобы добавить конкретные типы ресурсов в новый RC-файл.  
  
2.  В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.  
  
### <a name="to-create-a-new-resource-in-class-view"></a>Создание ресурса в представлении классов  
  
1.  В [представлении классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)щелкните правой кнопкой мыши нужный класс, выберите в контекстном меню команду **Добавить**, а затем выберите пункт **Добавить ресурс** .  
  
2.  В [диалоговом окне "Добавить ресурс"](../windows/add-resource-dialog-box.md)выберите тип ресурса, который хотите добавить в проект.  
  
### <a name="to-create-a-new-resource-from-the-project-menu"></a>Создание ресурса из меню "Проект"  
  
1.  В меню **Проект** выберите команду **Добавить ресурс**.  
  
 При создании нового ресурса Visual C++ присваивает ему уникальное имя, например, IDD_Dialog1. Этот идентификатор ресурса можно изменить путем редактирования свойств ресурса в соответствующем редакторе или в [окне свойств](/visualstudio/ide/reference/properties-window).  
  
 Вы можете создать ресурс как новый ресурс с параметрами по умолчанию (ресурс, созданный не по шаблону) или как ресурс на основе [шаблона](../windows/how-to-use-resource-templates.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.*  
  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)   
 [Диалоговое окно "Добавление ресурса"](../windows/add-resource-dialog-box.md)