---
title: -Fx (объединение подставляемого кода) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
dev_langs:
- C++
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 078019be2a1f818e9dd41acd3db2bced5fbda258
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="fx-merge-injected-code"></a>/Fx (объединение подставляемого кода)
Создает копию всех исходных файлов с подставляемым кодом, объединенным с исходным кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fx  
```  
  
## <a name="remarks"></a>Примечания  
 Чтобы отделить объединенный исходный файл от оригинального исходного файла, **/Fx** добавляет расширение MRG между именем файла и его расширением. Например, файл с именем MyCode.cpp, который включает код с атрибутами и собран с помощью с **/Fx** , порождает файл с именем MyCode.mrg.cpp, который содержит следующий код:  
  
```  
//+++ Start Injected Code  
[no_injected_text(true)];      // Suppress injected text, it has   
                               // already been injected  
#pragma warning(disable: 4543) // Suppress warnings about skipping   
                               // injected text  
#pragma warning(disable: 4199) // Suppress warnings from attribute   
                               // providers  
//--- End Injected Code  
```  
  
 В MRG-файле код, подставленный из-за наличия атрибута, будет отделен следующим образом:  
  
```  
//+++ Start Injected Code  
...  
//--- End Injected Code  
```  
  
 Атрибут [no_injected_text](../../windows/no-injected-text.md) встроен в MRG-файл, что допускает компиляцию MRG-файла без повторной подстановки текста.  
  
 Обратите внимание, что исходный MRG-файл предназначен для представления исходного кода, подставленного компилятором. MRG-файл может компилироваться или запускаться отличным от оригинального исходного файла образом.  
  
 Макросы не будут развернуты в MRG-файле.  
  
 Если программа включает файл заголовка, который использует подставляемый код, **/Fx** создает файл с расширением .mrg.h для этого заголовка. **/Fx** не выполняет объединение для включаемых файлов, которые не используют подставляемый код.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Откройте страницу свойств **Выходные файлы** .  
  
4.  Измените свойство **Раскрывать атрибуты исходного кода** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)