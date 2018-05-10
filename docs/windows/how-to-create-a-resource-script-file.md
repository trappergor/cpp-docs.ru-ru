---
title: 'Как: Создание файла описания ресурсов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a15352640a39ff6adc3b5a956a1f32c9fd414272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-create-a-resource-script-file"></a>Практическое руководство. Создание файла описания ресурсов
> [!NOTE]
>  Редактор ресурсов недоступен в выпусках Express.  
>   
>  Этот материал относится к классическим приложениям Windows. В проектах на языках .NET файлы описания ресурсов не используются. Дополнительные сведения см. в разделе [Файлы ресурсов](../windows/resource-files-visual-studio.md).  
  
### <a name="to-create-a-new-resource-script-rc-file"></a>Создание файла описания ресурсов (RC)  
  
1.  Выберите в `Solution Explorer`папку существующего проекта, например MyProject.  
  
    > [!NOTE]
    >  Не перепутайте папку проекта с папкой решения в обозревателе решений. Если поместить фокус на папке решения, в диалоговом окне **Добавление нового элемента** (в шаге 3) будут отображаться другие варианты.  
  
2.  В меню **Проект** выберите пункт **Добавить новый элемент**.  
  
3.  В диалоговом окне **Добавление нового элемента** выберите папку **Visual C++** , а затем выберите в правой области **Файл ресурсов (.rc)** .  
  
4.  Укажите имя файла описания ресурсов в текстовом поле **Имя** и нажмите кнопку **Открыть**.  
  
 Теперь можно [создать](../windows/how-to-create-a-resource.md) ресурсы и добавить их в RC-файл.  
  
> [!NOTE]
>  Файл описания ресурсов (RC) можно добавить только в существующий проект, загруженный в интегрированную среду разработки Visual Studio. Нельзя создать автономный RC-файл (за пределами проекта). [Шаблоны ресурсов](../windows/how-to-use-resource-templates.md) (RCT-файлы) можно создать в любой момент.  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)