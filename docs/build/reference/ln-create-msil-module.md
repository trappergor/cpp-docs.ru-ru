---
title: "-LN (Создание модуля MSIL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /LN
dev_langs: C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0278d59af9a62393f90a91655e3d7f0323e08118
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ln-create-msil-module"></a>/LN (создание модуля MSIL)
Указывает, что манифест сборки не должен быть включен в выходной файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/LN  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию **/LN** не действует (манифест сборки вставляется в выходной файл).  
  
 Когда **/LN** используется, один из [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметры также должны использоваться.  
  
 Управляемая программа, которая не содержит метаданных сборки в манифесте, называется модуля. Если компиляция выполняется с [/c (компиляция без связывания)](../../build/reference/c-compile-without-linking.md) и **/LN**, укажите [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.  
  
 Вы можете создать модули, если вы хотите использовать подход на основе компонентов для создания сборок.  То есть можно создавать типы и компилировать их в модули.  Затем можно создать сборку из одного или нескольких модулей.  Дополнительные сведения о создании сборок из модулей см. в разделе [.netmodule качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md) или [компоновщик сборок (Al.exe)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
 Расширение файла по умолчанию для модуля: NETMODULE.  
  
 В [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] версиях до Visual C++ 2005 модуль был создан с **/clr:noAssembly**.  
  
 Компоновщик Visual C++ в качестве входных данных принимает NETMODULE-файлы и будет выходной файл, создаваемый компоновщиком, сборка или NETMODULE-файл с не зависят от времени выполнения на любом netmodules-файлы, которые были введены в компоновщик.  Дополнительные сведения см. в разделе [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
-   Укажите [/NOASSEMBLY (Создание модуля MSIL)](../../build/reference/noassembly-create-a-msil-module.md) на фазе компоновщика, чтобы создать выходной файл.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   Данного параметра компилятора программным способом нельзя.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)