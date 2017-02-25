---
title: "/MANIFESTDEPENDENCY (Указать зависимости манифеста) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AdditionalManifestDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTDEPENDENCY - параметр компоновщика"
  - "MANIFESTDEPENDENCY - параметр компоновщика"
  - "-MANIFESTDEPENDENCY - параметр компоновщика"
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTDEPENDENCY (Указать зависимости манифеста)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## Заметки  
 \/MANIFESTDEPENDENCY позволяет определить атрибуты, которые помещаются в разделе \<dependency\> файла манифеста.  
  
 Дополнительные сведения о создании файла манифеста см. в разделе [\/MANIFEST \(создание манифеста параллельной сборки\)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md).  
  
 Дополнительные сведения см. в разделе \<dependency\> файла манифеста см. в разделе [Файлы конфигурации издателя](http://msdn.microsoft.com/library/aa375682).  
  
 Сведения, заданные с помощью \/MANIFESTDEPENDENCY, можно передать компоновщику двумя способами:  
  
-   Непосредственно в командной строке \(или в файле ответов\) с помощью параметра \/MANIFESTDEPENDENCY.  
  
-   С помощью директивы pragma [comment](../../preprocessor/comment-c-cpp.md).  
  
 В следующем примере кода показано примечание \/MANIFESTDEPENDENCY, переданное с помощью директивы pragma,  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 в результате чего в файле манифеста появляется следующая запись:  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 То же самое примечание \/MANIFESTDEPENDENCY можно передать с помощью командной строки:  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 Компоновщик соберет примечания \/MANIFESTDEPENDENCY, удалит повторяющиеся записи, а затем добавит результирующую строку XML в файл манифеста.  Если компоновщик обнаружит конфликтующие записи, файл манифеста будет поврежден и приложение не будет запускаться \(в журнал событий будет добавлена запись о причине сбоя\).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Файл манифеста**.  
  
5.  Измените свойство **Дополнительные зависимости манифеста**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)