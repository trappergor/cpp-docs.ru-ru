---
title: "-bigobj (увеличение количество разделов. OBJ-файл) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bigobj
dev_langs: C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 384ec0de9e5cb1b3172b980bf7f412abe759ff91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (Увеличение количества разделов в OBJ-файле)
**/ bigobj** увеличивает количество разделов, которые может содержать объектный файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию объектный файл может содержать до 65 536 байт (2 ^ 16) адресных секций. Это происходит независимо от того, что указан целевой платформы. **/ bigobj** увеличивает его адресную емкость до 4 294 967 296 (2 ^ 32).  
  
 Большинство модулей никогда не создаст OBJ-файл, содержащий более чем 65 536 разделов. Однако машины созданный код или код с интенсивным использованием библиотеки шаблонов может потребоваться OBJ-файлы, которые могут содержать дополнительные разделы. **/ bigobj** включена по умолчанию для проектов магазина Windows, так как код XAML сгенерированных включает большое количество заголовков. Если отключить этот параметр на проект приложения для магазина Windows, желательно возникает ошибка компилятора C1128.  
  
 Компоновщики, входящие в до Visual C++ 2005 не удается прочитать OBJ-файлы, которые были созданы при помощи **/bigobj**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)