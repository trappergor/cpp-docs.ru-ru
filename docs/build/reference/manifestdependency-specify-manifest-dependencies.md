---
title: "-MANIFESTDEPENDENCY (указать зависимости манифеста) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs: C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01da83a57769dbe5b86c5bc2a73875231b769cdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Указать зависимости манифеста)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>Примечания  
 / MANIFESTDEPENDENCY позволяет указать атрибуты, которые будут помещены в \<зависимостей > раздел файла манифеста.  
  
 В разделе [параметр/MANIFEST (Создание Side-by-Side манифеста сборки)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) сведения о том, как создать файл манифеста.  
  
 Дополнительные сведения о \<зависимостей > раздел файла манифеста, в разделе [файлов конфигурации издателя](http://msdn.microsoft.com/library/aa375682).  
  
 / MANIFESTDEPENDENCY информация может быть передана в компоновщик одним из двух способов:  
  
-   Непосредственно в командной строке (или в файле ответов) с помощью параметра/MANIFESTDEPENDENCY.  
  
-   Через [комментарий](../../preprocessor/comment-c-cpp.md) pragma.  
  
 В следующем примере показано комментария/MANIFESTDEPENDENCY, переданная с помощью директивы pragma  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 что приводит к следующей записи в файл манифеста:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Одинаковые примечания/MANIFESTDEPENDENCY может быть передан в командной строке следующим образом:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 Компоновщик соберет примечания/MANIFESTDEPENDENCY, удалит повторяющиеся записи и затем добавьте результирующую строку XML в файл манифеста.  Если компоновщик обнаруживает конфликтующие записи, файл манифеста будет поврежден и приложение не запустится (будет добавлена запись в журнал событий, указывающий источник сбоя).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **файл манифеста** страницу свойств.  
  
5.  Изменить **Дополнительные зависимости манифеста** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)