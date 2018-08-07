---
title: Предварительный просмотр ресурсов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff41dd0aad30382eb5229679054a74526652737
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605023"
---
# <a name="previewing-resources"></a>Предварительный просмотр ресурсов
Предварительный просмотр ресурсов позволяет просматривать графические ресурсы, не открывая их. Предварительный просмотр также полезна для исполняемых файлов после компиляции так, как изменить идентификаторы ресурсов в числа. Так как эти числовые идентификаторы часто не предоставляет достаточно сведений, предварительный просмотр ресурсов позволяет быстро находить их.  
  
 Можно предварительно просмотреть визуальное расположение следующих типов ресурсов:  
  
-   Bitmap  
  
-   Диалоговое окно  
  
-   Значок  
  
-   Меню  
  
-   Курсор  
  
-   Toolbar  
  
 Функцию предварительного просмотра не применяется к ресурсам сочетаний клавиш, манифест, таблица строк и сведения о версии.  
  
### <a name="to-preview-resources"></a>Предварительный просмотр ресурсов  
  
1.  В [представление ресурсов](../windows/resource-view-window.md) или в окне документа выберите ресурс, например IDD_ABOUTBOX.  
  
     **Примечание** Если проект еще не содержит RC-файл, см. статью [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [окно "Свойства"](/visualstudio/ide/reference/properties-window), нажмите кнопку **страницы свойств** кнопки.  
  
     \- или -  
  
3.  На **представление** меню, щелкните **страницы свойств**.  
  
     Предварительный просмотр этого ресурса открывшейся странице свойств для ресурса. Затем можно вверх и вниз со стрелками для перемещения в структуре дерева в представлении ресурсов или окна документа. Страницы свойств будет оставаться открытым и отображать любой ресурс, который имеет фокус и возможность предварительного просмотра.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования 
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Открытие файла описания ресурсов за пределами проекта (в автономном режиме)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [Редакторы ресурсов](../windows/resource-editors.md)