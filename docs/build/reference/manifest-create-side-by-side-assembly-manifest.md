---
title: "/MANIFEST (создание манифеста параллельной сборки) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateManifest"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFEST - параметр компоновщика"
  - "MANIFEST - параметр компоновщика"
  - "-MANIFEST - параметр компоновщика"
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# /MANIFEST (создание манифеста параллельной сборки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## Заметки  
 Параметр \/MANIFEST определяет, что компоновщик должен создать параллельный файл манифеста.  Дополнительные сведения о файлах манифеста см. в разделе [Manifest Files Reference](http://msdn.microsoft.com/library/aa375632).  
  
 По умолчанию используется параметр \/MANIFEST.  
  
 Параметр \/MANIFEST:EMBED указывает, что компоновщику следует внедрить файл манифеста в образе в качестве ресурса RT\_MANIFEST типа.  Необязательный параметр `ID` идентификатора ресурса, который будет использоваться для манифеста.  Используйте значение 1 для исполняемого файла.  Используйте значение 2 для библиотеки DLL, чтобы разрешить его определение закрытых зависимости.  Если параметр `ID` не указан, используется значение по умолчанию 2, если задан параметр \/DLL; в противном случае значение по умолчанию 1.  
  
 Начиная с [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], в файлах манифестов для исполняемых файлов имеется раздел, в котором указываются данные по контролю учетных записей \(UAC\).  Если указать \/MANIFEST, но определяется как [\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) или [\/DLL](../../build/reference/dll-build-a-dll.md), фрагмент функции контроля учетных записей по умолчанию, имеет уровень контроля учетных записей, равным *asInvoker* вставляется в манифест.  Дополнительные сведения об уровнях контроля учетных записей см. в описании [\/MANIFESTUAC \(встраивает в манифест сведений об UAC\)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Чтобы изменить реакция на событие по умолчанию для контроля учетных записей, выполните одно из следующих:  
  
-   Задайте параметр \/MANIFESTUAC и укажите уровень контроля учетных записей нужное значение.  
  
-   Или задайте параметр \/MANIFESTUAC:NO, если не требуется создать фрагмент функции контроля учетных записей в манифесте.  
  
 Если не указать \/MANIFEST и указать комментарии [\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md), создается файл манифеста.  Файл манифеста не создается при определении \/MANIFEST:NO.  
  
 Если указать \/MANIFEST, имя файла манифеста совпадает с именем выбранного выходного файла, но с MANIFEST в соответствии с именем файла.  Например, если имя файла вывода MyFile.exe очевидным, имя файла MyFile.exe.manifest.  Если указать \/MANIFESTFILE:,*name* манифеста, имя которого задается *name*.  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Файл манифеста**.  
  
5.  Измените свойство **Создавать манифест**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)