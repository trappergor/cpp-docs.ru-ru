---
title: -VERSION (сведения о версии) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs:
- C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 092fd11d7bf062afb59c9b33d620624c63b5e01f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378994"
---
# <a name="version-version-information"></a>/VERSION (Сведения о версии)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *Основные*и *дополнительный номер*  
 Номер версии в заголовке файла .exe или .dll.  
  
## <a name="remarks"></a>Примечания  
 Параметр/Version предписывает компоновщику поставить номер версии в заголовке файла .exe или .dll. Использование служебной программы DUMPBIN [/Headers](../../build/reference/headers.md) для просмотра значения поля версии образа НЕОБЯЗАТЕЛЬНЫХ значений ЗАГОЛОВКА, чтобы увидеть эффект/Version.  
  
 *Основных* и *дополнительный* аргументами являются десятичные числа в диапазоне от 0 до 65 535. Значение по умолчанию используется версия 0.0.  
  
 Сведения, указанные с/Version не влияет на сведения о версии, который отображается для приложения при просмотре его свойства в проводнике. Что сведения о версии берется из файла ресурсов, который используется для построения приложения. В разделе [редактор сведений о версии](../../windows/version-information-editor.md) для получения дополнительной информации.  
  
 Другой способ вставить номер версии — [версии](../../build/reference/version-c-cpp.md) оператор определения модуля.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Общие** страницу свойств.  
  
4.  Изменить **версии** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)