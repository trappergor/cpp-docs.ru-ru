---
title: "-Gy (включение компоновки на уровне функций) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs: C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebe272b12a503a310319526f53f312a033a0ee26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="gy-enable-function-level-linking"></a>/Gy (включение компоновки на уровне функций)
Компилятор может упаковывать отдельные функции в форме упакованных функций (COMDAT).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Gy[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Компоновщик требует, что функции упаковывать отдельно как COMDAT, чтобы исключить или упорядочить отдельные функции в файл DLL или .exe.  
  
 Можно использовать параметр компоновщика [/OPT (оптимизации)](../../build/reference/opt-optimizations.md) исключаемый неиспользуемые упакованные функции из файла .exe.  
  
 Можно использовать параметр компоновщика [/Order (Put функций по порядку)](../../build/reference/order-put-functions-in-order.md) для помещения упакованных функций в указанном порядке, в файл .exe.  
  
 Встроенные функции всегда упаковываются, если их экземпляры создаются в качестве вызовов (это, например, происходит, если встраивание является отключены или используется адрес функции). Кроме того определенные в объявлении класса функций-членов C++ упаковываются автоматически; другие функции — это не, и при выборе этого параметра требуется компилировать их как упакованные функции.  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) автоматически задает параметр, используемый изменить и продолжить, **/Gy** параметр.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **создания кода** страницу свойств.  
  
4.  Изменить **включение компоновки на уровне функций** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)