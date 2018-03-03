---
title: "-WL (включить однострочные диагностические) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48ba6ab05ac596c98c4fa5a95971735c62267a35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (включение вывода однострочных диагностических сообщений)
Дополнительные данные добавляются на ошибку или предупреждение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/WL  
```  
  
## <a name="remarks"></a>Примечания  
 Ошибки и предупреждения компилятора C++ может следовать дополнительную информацию, которая отображается по умолчанию в новой строке. При компиляции из командной строки, можно добавить дополнительную строку сведения ошибке или предупреждающее сообщение. Это может быть нежелательно, если записать выходные данные сборки в файл журнала и обработке этого файла, чтобы найти все ошибки и предупреждения. Точка с запятой будет отдельные дополнительной строки ошибок и предупреждений.  
  
 Не все ошибки и предупреждения содержат дополнительную строку данных. Следующий код будет создавать ошибку, которая имеет дополнительную строку сведения; Это позволит проверить результат, при использовании **/WL**.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
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