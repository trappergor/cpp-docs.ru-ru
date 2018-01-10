---
title: "-Zc: forScope (принудительное обеспечение соответствия в области цикла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
dev_langs: C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 243966ae5e8c7d0792f40206adc9d0ae3b2fb673
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)
Использовался для реализации стандартного поведения C++ для циклов [for](../../cpp/for-statement-cpp.md) с расширениями Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  По умолчанию параметр**/Zc:forScope** включен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:forScope[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр **/Zc:forScope-** не рекомендуется к использованию и будет удален в одном из следующих выпусков. Использование **/Zc:forScope-** приводит к созданию предупреждения D9035 о нерекомендуемом элементе.  
  
 При стандартном поведении инициализатору цикла **for** позволяется выходить за пределы области после цикла **for** . При использовании **/Zc:forScope-** и [/Ze](../../build/reference/za-ze-disable-language-extensions.md)инициализатор цикла **for** остается в пределах области до завершения локальной области.  
  
 Приведенный ниже код компилируется при использовании параметра **/Ze** , но не при использовании **/Za**.  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 Если используется параметр **/Zc:forScope-**, то каждый раз, когда переменная будет попадать в область из-за ее объявления в предыдущей области, будет выдаваться предупреждение C4288 (оно отключено по умолчанию). Для иллюстрации этого поведения в примере кода необходимо убрать символы `//` для объявления `int i`.  
  
 Поведение параметра **/Zc:forScope** во время выполнения можно изменить с помощью директивы pragma [conform](../../preprocessor/conform.md) .  
  
 При использовании параметра **/Zc:forScope-** в проекте с существующим файлом PCH выдается предупреждение, параметр **/Zc:forScope-** пропускается, а компиляция продолжается c использованием существующих файлов PCH. Если требуется создать новый файл PCH, используйте [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md).  
  
 Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В области навигации откройте страницу свойств **Свойства конфигурации**, **C/C++**, **Язык** .  
  
3.  Измените свойство **Обеспечение согласования видимости переменных, объявленных в заголовке оператора for** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)   
 [/ Za, /Ze (отключить расширения языка)](../../build/reference/za-ze-disable-language-extensions.md)