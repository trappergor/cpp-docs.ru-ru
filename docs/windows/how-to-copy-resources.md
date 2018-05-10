---
title: 'Как: копирование ресурсов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b173be24e9f177a3156f740fcb07240c30fec75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-copy-resources"></a>Практическое руководство. Копирование ресурсов
Можно копировать ресурсы из одного файла в другой без изменений или вы можете [измените язык или условие ресурса при копировании](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Ресурсы можно легко скопировать из существующего ресурса или исполняемого файла для текущего файла ресурсов. Для этого откройте обоих файлов, которые содержат ресурсы, в то же время и перетащите элементы из одного файла, или скопируйте и вставьте между двумя файлами. Этот метод работает для RC-файлы ресурсов и файлы ресурсов (.rct) шаблона, а также исполняемых файлов (.exe).  
  
> [!NOTE]
>  Visual C++ включает образцы ресурсных файлов, которые можно использовать в приложении. Дополнительные сведения см. в разделе [CLIPART: общие ресурсы](http://msdn.microsoft.com/en-us/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Можно использовать метод перетаскивания и вставки между RC-файлов, открытых [за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Копирование ресурсов между файлами с помощью метода перетаскивания и вставки  
  
1.  Откройте отдельно два файла ресурсов (Дополнительные сведения см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Например, откройте Source1.rc и Source2.rc.  
  
2.  В первом RC-файле щелкните ресурс, который нужно скопировать. Например в Source1.rc, щелкните IDD_DIALOG1.  
  
3.  Удерживая нажатой клавишу CTRL и перетащите ресурс во второй RC-файл. Например перетащите IDD_DIALOG1 из Source1.rc Source2.rc.  
  
    > [!NOTE]
    >  Перетаскивание ресурса без удерживания нажатой клавишей CTRL Перемещение ресурса, а не его копирования.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>Для копирования ресурсов с помощью копирования и вставки  
  
1.  Откройте отдельно два файла ресурсов (Дополнительные сведения см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Например, Source1.rc и Source2.rc.  
  
2.  В исходном файле, с которого вы хотите скопировать ресурс (например, Source1.rc), щелкните правой кнопкой мыши ресурс и выберите **копирования** в контекстном меню.  
  
3.  Щелкните правой кнопкой мыши файл ресурсов, в который вы хотите добавить ресурс (например, Source2.rc). Выберите **вставить** в контекстном меню.  
  
    > [!NOTE]
    >  Невозможно перетащите и удалить, копировать, Вырезать или вставку между файлами ресурсов в проект (представление ресурса) и автономными файлами .rc (которые открытыми в окнах документа). Это можно сделать в предыдущих версиях продукта.  
  
    > [!NOTE]
    >  Чтобы избежать конфликтов с именами и значениями в существующем файле, Visual C++ может изменить значение символа копируемого ресурса или имя и значение, при попытке скопировать в новый файл.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Как: открытие файла описания ресурсов за пределами проекта (автономный)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)