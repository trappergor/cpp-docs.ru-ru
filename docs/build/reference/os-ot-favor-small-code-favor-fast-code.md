---
title: -Os -Ot (приоритет размера кода кода) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
dev_langs:
- C++
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f97ab0a53eb82b65149ea0f27139743e065f7ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378913"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (приоритет размера кода или скорости кода)
Сводит к минимуму или максимизирует размер exe и DLL.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Os  
/Ot  
```  
  
## <a name="remarks"></a>Примечания  
 **/ OS** (приоритет размера кода) минимизирует размер exe-и DLL-библиотеки, предписывая компилятору предпочитать размер скорости. Компилятор может сократить многие конструкции C и C++ для функциональных возможностей схожих последовательность машинного кода. Иногда эти различия обеспечивают компромиссы или скоростью. **/Os** и **/Ot** параметры позволяют указать предпочтение отдается:  
  
 **/Ot** (предпочтителен кода) повышает скорость exe-и DLL-библиотеки, предписывая компилятору предпочитать размер скорости. (Это значение по умолчанию). Компилятор может сократить многие конструкции C и C++ для функциональных возможностей схожих последовательность машинного кода. В некоторых случаях эти различия обеспечивают компромиссы или скоростью. Параметр /Ot подразумевается Максимальная скорость ([/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)) параметра. **/O2** объединяет несколько возможностей для создания кода, очень быстро.  
  
 Если вы используете **/Os** или **/Ot**, то необходимо также указать [/Og](../../build/reference/og-global-optimizations.md) для оптимизации кода.  
  
> [!NOTE]
>  Сведения, полученные при тестах профилирования, переопределяют оптимизации, которые в противном случае вступят в силу при указании **/Ob**, **/Os**, или **/Ot**. Для получения дополнительной информации [профильные оптимизации](../../build/reference/profile-guided-optimizations.md).  
  
 **x86 конкретных**  
  
 В следующем примере кода показано различие между приоритет размера кода (**/Os**) параметры и предпочтения быстрого кода (**/Ot**) параметра:  
  
> [!NOTE]
>  Ниже описывается ожидаемое поведение при использовании **/Os** или **/Ot**. Тем не менее поведение компилятора от версии к версии может привести к разных оптимизаций для приведенный ниже код.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 Как показано в следующем фрагменте машинного кода, когда DIFFER.c предпочтением размер (**/Os**), компилятор реализует выражение умножения в инструкции return явно, как умножение, для создания последовательности короткое, но медленнее кода:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 Кроме того, когда DIFFER.c с предпочтением скорости (**/Ot**), компилятор реализует выражение умножения в оператор return, как ряд shift и `LEA` инструкции для создания последовательности быстрее, но больше кода:  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **КОНЕЦ x86 конкретных**  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **оптимизации** страницу свойств.  
  
4.  Изменить **предпочитать размер или скорость** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)