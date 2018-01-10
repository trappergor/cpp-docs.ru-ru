---
title: "-Oi (Создание встроенных функций) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs: C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0a24830dbc67466e52f3f3c488dda7ac5b4778d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (создание встроенных функций)
Заменяет вызов некоторых функций с формами внутреннего или в противном случае специальные функции, помогающие ваше приложение будет выполняться быстрее.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Oi[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Программы, в которых используются встроенные функции выполняются быстрее, поскольку они не имеют нагрузке вызовов функций, но могут быть большего размера из-за создания дополнительного кода.  
  
 В разделе [встроенная функция](../../preprocessor/intrinsic.md) Дополнительные сведения о функциях, имеющих встроенные формы.  
  
 **/Oi** представляет собой запрос компилятору заменить некоторые вызовы функций встроенные функции; компилятор может вызывать функцию (и не заменять вызов функции на встроенную форму) Если это приведет к повышению производительности.  
  
 **x86 конкретных**  
  
 Встроенные функции с плавающей запятой не выполнения каких-либо специальных проверок входных значений так работают в ограниченных диапазоны входных данных и обработки различных исключений и граничные условия, чем библиотечные процедуры с тем же именем. Использование встроенных форм означает потерю обработки исключений IEEE и потере `_matherr` и `errno` функциональные возможности; второе означает потерю соответствия стандарту ANSI. Однако встроенных форм может значительно ускорить выполнение программ интенсивной с-плавающей запятой и для большинства приложений являются проблемы соответствия запятой.  
  
 Можно использовать [Za](../../build/reference/za-ze-disable-language-extensions.md) параметр компилятора для переопределения поколения true встроенных параметров с плавающей запятой. В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.  
  
 **КОНЕЦ x86 конкретных**  
  
 Можно также использовать [встроенная функция](../../preprocessor/intrinsic.md) создание встроенных функций или [функции (C/C++)](../../preprocessor/function-c-cpp.md) чтобы явно принудительно задать вызов функции.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **оптимизации** страницу свойств.  
  
4.  Изменить **включить встроенные функции** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Встроенные инструкции компилятора](../../intrinsics/compiler-intrinsics.md)