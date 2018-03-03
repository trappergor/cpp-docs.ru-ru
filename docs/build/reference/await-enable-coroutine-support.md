---
title: "-await (Включение поддержки соподпрограмме) | Документы Microsoft"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47134532b16d1b5a907e4ed3170a0827316d7c65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="await-enable-coroutine-support"></a>/ await (Включение поддержки соподпрограмме)  
  
Используйте **/ await** параметр компилятора, чтобы обеспечить поддержку компилятора сопрограммы.  
  
## <a name="syntax"></a>Синтаксис  
  
> / await  
  
## <a name="remarks"></a>Примечания  
  
**/ Await** параметр компилятора включает поддержку компилятора для C++ сопрограммы и ключевые слова **co_await**, **co_yield**, и **co_return**. По умолчанию она отключена. Сведения о поддержке сопрограммы в Visual Studio см. в разделе [блоге команды разработчиков Visual Studio](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Дополнительные сведения о предложении standard сопрограммы см. в разделе [N4628 работа черновика, технической спецификации C++ расширений для сопрограммы](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).  

**/ Await** параметр доступна в Visual Studio 2015.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1. Откройте свой проект **страницы свойств** диалоговое окно.   
  
2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.  
  
3. Введите **/ await** параметра компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
  
[Параметры компилятора](../../build/reference/compiler-options.md)   
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)