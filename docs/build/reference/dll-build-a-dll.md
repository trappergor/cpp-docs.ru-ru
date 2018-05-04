---
title: -DLL (построение библиотеки DLL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1767ac9ef063ace2ee9d567dd9038519afababf8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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