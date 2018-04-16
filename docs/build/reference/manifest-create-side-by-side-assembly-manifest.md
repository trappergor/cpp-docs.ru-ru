---
title: -МАНИФЕСТА (Создание манифеста сборки Side-by-Side) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb26957109a558b48d6252e042e9082f7357fbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (создание манифеста параллельной сборки)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр / MANIFEST указывает, что компоновщик должен создать файл манифеста side-by-side. Дополнительные сведения о файлах манифеста см. в разделе [файлы манифеста ссылаются](http://msdn.microsoft.com/library/aa375632).  
  
 По умолчанию используется параметр/MANIFEST.  
  
 Параметр/MANIFEST: внедрить параметр указывает, что компоновщик должен внедрять файл манифеста в образе как ресурс типа RT_MANIFEST. Необязательный `ID` параметр — идентификатор ресурса для использования для манифеста. Используйте значение 1 для исполняемого файла. Используйте значение 2 для библиотеки DLL для указания закрытого зависимостей. Если `ID` параметр не указан, значение по умолчанию — 2, если задан параметр/DLL; в противном случае — значение по умолчанию — 1.  
  
 Файлы манифеста для исполняемых файлов, начиная с Visual Studio 2008, содержать раздел, в котором указываются сведения управления учетных записей (UAC). Если указан параметр/MANIFEST, но не указать [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) , ни [/DLL](../../build/reference/dll-build-a-dll.md), фрагмент контроля учетных Записей по умолчанию значением уровня контроля учетных Записей для *asInvoker* вставляется в манифест. Дополнительные сведения об уровнях контроля учетных Записей см. в разделе [/MANIFESTUAC (встраивает UAC сведения в манифесте)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Чтобы изменить поведение по умолчанию для контроля учетных Записей, выполните одно из следующих:  
  
-   Укажите параметр/MANIFESTUAC и на уровне нужное значение.  
  
-   Или задайте параметр/MANIFESTUAC: No, если вы не хотите создать фрагмент контроля учетных Записей в манифесте.  
  
 Если не указан параметр/MANIFEST, но указано [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) комментариях, создается файл манифеста. Файл манифеста не создается при указании /MANIFEST:NO.  
  
 Если указан параметр/MANIFEST, имя файла манифеста совпадает имя выходного файла, но с расширением MANIFEST в имя файла. Например если MyFile.exe имени выходного файла, имя файла манифеста — MyFile.exe.manifest.  Если параметр/MANIFESTFILE:*имя*, имя манифеста является то, что указано в *имя*.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **файл манифеста** страницу свойств.  
  
5.  Изменить **создать манифест** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)