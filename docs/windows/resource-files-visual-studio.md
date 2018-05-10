---
title: Файлы ресурсов (Visual Studio) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio]
- .rc files
- resource files
- resource script files
- resource script files, Win-32 based applications
- resource script files, files updated when editing resources
- resources [Visual Studio], types of resource files
- rct files
- resources [C++]
- rc files
- resource files, types of
- .rct files
- resource script files, unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b4b56d1f329aee29c37b15590729074d305f04d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="resource-files-visual-studio"></a>Файлы ресурсов (Visual Studio)
> [!NOTE]
>  Этот материал относится к классическим приложениям Windows. Сведения о ресурсах в приложениях универсальной платформы Windows см. в разделе [определение ресурсов приложения](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4).  
>   
> Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
>  
> . Так как в проектах на языках программирования .NET не используются файлы описания ресурсов, ресурсы необходимо открывать из **обозревателя решений**. Для работы с файлами ресурсов в управляемых проектах можно использовать [редактор изображений](../windows/image-editor-for-icons.md) и [двоичный редактор](binary-editor.md) . Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.  
  
 Термин "файл ресурсов" может относиться к ряду типов файлов, включая следующие:  
  
-   файл описания ресурсов программы (RC);  
  
-   файл шаблона ресурсов (RCT);  
  
-   ресурс, существующий в виде отдельного файла, например файл с растровым изображением, значком или курсором, на который имеется ссылка в файле RC;  
  
-   файл заголовка, созданный средой разработки, например Resource.h, на который есть ссылка в файле RC.  
  
 Ресурсы также могут находиться в [файлах других типов](../windows/editable-file-types-for-resources.md) , например EXE, DLL и RES. Вы можете работать с ресурсами и файлами ресурсов, включенными в текущий проект или не являющимися его частью. Также можно работать с файлами ресурсов, которые не были созданы в среде разработки Visual Studio. Например, с их помощью можно выполнять следующее.  
  
-   Работать с вложенными и условно включенными файлами ресурсов.  
  
-   Обновлять существующие ресурсы или преобразовывать их в формат Visual C++.  
  
-   Импортировать графические ресурсы в текущий файл ресурсов или экспортировать их из него.  
  
-   Включать общие или доступные только для чтения идентификаторы (символы), которые нельзя изменить с помощью среды разработки.  
  
-   Включать в исполняемый файл (EXE) ресурсы, которые не требуют редактирования (или не должны редактироваться) в процессе работы над текущим проектом, например ресурсы, используемые одновременно в нескольких проектах.  
  
-   Включать типы ресурсов, не поддерживаемые средой разработки.  
  
 В этом разделе рассматриваются следующие задачи:  
  
-   [Создание файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md)  
  
-   [Создание ресурса](../windows/how-to-create-a-resource.md)  
  
-   [Просмотр ресурсов в файле описания ресурсов](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [Открытие файла описания ресурсов в текстовом формате](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [Включение ресурсов во время компиляции](../windows/how-to-include-resources-at-compile-time.md)  
  
-   [Копирование ресурсов](../windows/how-to-copy-resources.md)  
  
-   [Использование шаблонов ресурсов (RCT)](../windows/how-to-use-resource-templates.md)  
  
-   [Импорт и экспорт ресурсов](../windows/how-to-import-and-export-resources.md)  
  
-   [Редактируемые типы файлов для ресурсов](../windows/editable-file-types-for-resources.md)  
  
-   [Файлы, на которые влияет редактирование ресурсов](../windows/files-affected-by-resource-editing.md)  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редакторы ресурсов](../windows/resource-editors.md)   
 [Работа с файлами ресурсов](../windows/working-with-resource-files.md)   
 [Меню и другие ресурсы](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

