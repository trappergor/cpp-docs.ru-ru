---
title: "-homeparams (копирование параметров регистра в стек) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fff1b206620ef9efee3fc22c83c8d5317e99b607
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (копирование параметров регистров в стек)
Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>Примечания  
 Данный параметр компилятора предназначен только для компиляторов [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] (машинная компиляция и кросс-компиляция).  
  
 При передаче параметров в [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] компиляции, соглашения о вызове требуется пространство стека для параметров, даже для параметров, переданных в регистрах. Дополнительные сведения см. в разделе [передача параметров](../../build/parameter-passing.md). Тем не менее по умолчанию в сборке выпуска параметров регистра не записывается в стек, в пространство, уже предоставленное для параметров. Это затрудняет отладочное построение оптимизированного (выпуск) программы.  
  
 Построение выпуска, используйте **/homeparams** чтобы убедиться, что можно отлаживать приложения. **/ homeparams** подразумевают недостаток производительности, поскольку он требует цикла для загрузки параметров регистра в стек.  
  
 В отладочном построении стек всегда заполняется параметры передаются в регистрах.  
  
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