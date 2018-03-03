---
title: "-GF (исключение повторяющихся строк) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs:
- C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d69e892fb9487b66da4dfa2a801bab302e962af7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Исключение повторяющихся строк)
Позволяет компилятору создавать одну копию одинаковых строк в образе программы и в памяти во время выполнения. Это такая оптимизация называется *объединение строк* , можно создавать более мелкие программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GF  
```  
  
## <a name="remarks"></a>Примечания  
 Если вы используете **/GF**, операционная система не меняет местами строковые части памяти и может считывать строки обратно из файла образа.  
  
 **/GF** пулы строк только для чтения. При попытке изменить строки в **/GF**, возникает ошибка приложения.  
  
 Объединение строк позволяет назначить несколько указателей на несколько буферов для нескольких указателей на один буфер. В следующем коде `s` и `t` инициализируются с такой же строки. Объединение строк вызывает указатель на общую память.  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) автоматически задает параметр, используемый изменить и продолжить, **/GF** параметр.  
  
> [!NOTE]
>  **/GF** параметр компилятора создает адресуемый раздел для каждого уникальная строка. И по умолчанию объектный файл может содержать до 65 536 адресуемых секций. Если программа содержит более 65 536 строк, используйте [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) параметр компилятора, чтобы создать дополнительные разделы.  
  
 **/GF** вступает в силу, когда [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) или **/O2** используется.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **создания кода** страницу свойств.  
  
4.  Изменить **включить объединение строк** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)