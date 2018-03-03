---
title: "-DLL (построение библиотеки DLL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a501590e127e5f27a465366611b4dbf3be175c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dll-build-a-dll"></a>/DLL (построение библиотеки DLL)
```  
/DLL  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/dll выполняет построение библиотеки DLL в качестве основного выходного файла. Обычно библиотека DLL содержит экспорты, которые могут использоваться другой программой. Существует три метода для указания экспортов в рекомендуемом порядке использования:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) в исходном коде  
  
2.  [ЭКСПОРТОВ](../../build/reference/exports.md) инструкции в DEF-файла  
  
3.  [И экспорт](../../build/reference/export-exports-a-function.md) спецификации в команде LINK  
  
 Программа может использовать более одного метода.  
  
 Другой способ построения библиотеки DLL — с **БИБЛИОТЕКИ** оператор определения модуля. Параметры/Base и/DLL вместе эквивалентны **БИБЛИОТЕКИ** инструкции.  
  
 Не использовать этот параметр в среде разработки; Этот параметр предназначен для использования только в командной строке. Этот параметр задается при создании проекта библиотеки DLL с помощью мастера приложений.  
  
 Обратите внимание, что при создании библиотеки импорта в предварительном этапе перед созданием DLL-файла, вам необходимо использовать тот же набор объектных файлов при построении DLL-файл, как пройденный при сборке библиотеки импорта.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **свойства конфигурации** папки.  
  
3.  Нажмите кнопку **Общие** страницу свойств.  
  
4.  Изменить **тип конфигурации** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)